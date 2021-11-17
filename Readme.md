# SQL Part2 lab


* create database called `movies`
* create table called movies 
* fill the table with the following data 
* answer the following questions 

1. write a SQL query to find the movies with ID 905 or 907 or 917. Return movie title.


2. write a SQL query to find the actors who were cast in the movie 'Annie Hall'. Return actor first name, last name and role. 

3. write a SQL query to find the actors who have not acted in any movie between1990 and 2000. Return actor first name, last name, movie title and release year.

4. write a SQL query to find those years when a movie received a rating of 3 or 4. Sort the result in increasing order on movie year. Return move year. 

5. write a SQL query to find those movies that have at least one rating and received highest number of stars. Sort the result-set on movie title. Return movie title and maximum review stars.

6. write a SQL query to find those movies, which have received ratings. Return movie title, director first name, director last name and review stars.

7. write a SQL query to find the highest-rated movies. Return movie title, movie year, review stars and releasing country. 

```
CREATE TABLE movies.movie (
    mov_id integer NOT NULL,
    mov_title character(50),
    mov_year integer,
    mov_time integer,
    mov_lang character(15),
    mov_dt_rel date,
    mov_rel_country character(5)
);

CREATE TABLE movies.movie_cast (
    act_id integer NOT NULL,
    mov_id integer NOT NULL,
    role character(30)
);

CREATE TABLE movies.actor (
    act_id integer NOT NULL,
    act_fname character(20),
    act_lname character(20),
    act_gender character(1)
);

CREATE TABLE movies.rating (
    mov_id integer NOT NULL,
    rev_id integer NOT NULL,
    rev_stars numeric(4,2),
    num_o_ratings integer
);


CREATE TABLE movies.director (
    dir_id integer NOT NULL,
    dir_fname character(20),
    dir_lname character(20)
);

CREATE TABLE movies.movie_direction (
    dir_id integer NOT NULL,
    mov_id integer NOT NULL
);


```


```
INSERT into movies.movie (mov_id, mov_title, mov_year, mov_time, mov_lang, mov_dt_rel, mov_rel_country) 
values
(902	,"The Innocents",  1961,	100,	"English",   1962-02-19	,"SW"  ),
(901,"Vertigo" ,1958, 128, "English" ,958-08-24, "UK" ),
(903,"Lawrence of Arabia" ,	1962,	216,"English"  ,1962-12-11,	"UK"  );

 

COPY movies.movie (mov_id, mov_title, mov_year, mov_time, mov_lang, mov_dt_rel, mov_rel_country) FROM stdin;
901	"Vertigo"                                           	1958	128	"English"        	1958-08-24	"UK"   

902	The Innocents                                     	1961	100	English        	1962-02-19	SW   


903	Lawrence of Arabia                                	1962	216	English        	1962-12-11	UK   

904	The Deer Hunter                                   	1978	183	English        	1979-03-08	UK  

905	Amadeus                                           	1984	160	English        	1985-01-07	UK  

906	Blade Runner                                      	1982	117	English        	1982-09-09	UK  

907	Eyes Wide Shut                                    	1999	159	English        	\N	UK   

908	The Usual Suspects                                	1995	106	English        	1995-08-25	UK   
909	Chinatown                                         	1974	130	English        	1974-08-09	UK   
910	Boogie Nights                                     	1997	155	English        	1998-02-16	UK   
911	Annie Hall                                        	1977	93	English        	1977-04-20	USA  
912	Princess Mononoke                                 	1997	134	Japanese       	2001-10-19	UK   
913	The Shawshank Redemption                          	1994	142	English        	1995-02-17	UK   
914	American Beauty                                   	1999	122	English        	\N	UK   
915	Titanic                                           	1997	194	English        	1998-01-23	UK   
916	Good Will Hunting                                 	1997	126	English        	1998-06-03	UK   
917	Deliverance                                       	1972	109	English        	    	


COPY movies.movie_cast (act_id, mov_id, role) FROM stdin;
101	901	John Scottie Ferguson         
102	902	Miss Giddens                  
103	903	T.E. Lawrence                 
104	904	Michael                       
105	905	Antonio Salieri               
106	906	Rick Deckard                  
107	907	Alice Harford                 
108	908	McManus                       
110	910	Eddie Adams                   
111	911	Alvy Singer                   
112	912	San                           
113	913	Andy Dufresne                 
114	914	Lester Burnham                
115	915	Rose DeWitt Bukater           
116	916	Sean Maguire                  
117	917	Ed                            
118	918	Renton                        
120	920	Elizabeth Darko               
121	921	Older Jamal                   
122	922	Ripley                        
114	923	Bobby Darin                   
109	909	J.J. Gittes                   
119	919	Alfred Borden                 
\.


COPY movies.movie_direction (dir_id, mov_id) FROM stdin;
201	901
202	902
203	903
204	904
205	905
206	906
207	907
208	908
209	909
210	910
211	911
212	912
213	913
214	914
215	915
216	916
217	917
218	918
219	919
220	920
218	921
215	922
221	923
\.


``` 