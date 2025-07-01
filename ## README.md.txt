 ## README.md



# day 1 --> sql learning ---> learned about --> [ CHECK constraint ]

          ** what I learned is ---> 
             
          1) how to use CHECK constraint in MySQL
          
          2) use of "" IN "" istead of  "" OR "" …  

            eg :->## status varchar(20) CHECK IN(status('active','inactive','unknown','busy')); 
                   
                  ## status varchar(20) CHECK (status='active' OR status='inactive' OR status='unknown' OR status='busy');   

            ---> 2.1) so here we can see that using  "" OR ""every time is monotonus , burdensome and bulky also .
                 2.2) but if we use "" IN "" it justs SIMPLIFY our query and make very clear and simple to understand.

         3) we can't use same constraint (here CHECK constraint) multiple times in same column
            
            eg :-   CHECK (status = 'active') OR CHECK (status = 'inactive'); ---> using same constraint twice in same column --> ERROR..


       

      ### example code ----> 

          CREATE TABLE student 
        (
          id int primary key ,
          name varchar(100),
          status varchar(20) CHECK (status IN ('active', 'inactive')),
          age int CHECK (age=10 OR age=12)
        );


NOTE :--> CHECK works best with IN (instead of OR ) when validating multiple values. 
