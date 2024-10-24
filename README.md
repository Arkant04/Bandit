# Bandit
bandit0
host: bandit.labs.overthewire.org
puerto: 2220 
username: bandit0
password: bandit0

objetivo conectarnos por ssh al host y buscar un archivo 
readme con la password 

Esta contraseña la he encontrado usanso ls y en el he visto 
que me aparecia un readmea a lo que he puesto "cat readme" y 
hay dentro estaba el password este

password:ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

bandit1
para entrar en el bandit uno primero tenemos que poner "exit" 
para salir de bandit0, cuando he salido he puesto 
"bandit1@bandit.labs.overthewire.org -p 2220" cuando pulse 
enter me pidieron la contraseña la cual era: 
"ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If"

password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

para conseguir este password busque que eran los dashed 
filename  y encontre que poniendo "cat < -" podria sacar el 
password, cuando lo puse me salio esta con.

bandit2 

Cuando salgamos del bandit1 y nos metamos en el dos y metamos
la contraseña, este nivel nos pedira meternos en un archivo 
con un nombre con espacios para esto pondremos lo siguiente 
"cat'nombre de carpeta espaciada'" con esto ya tendremos el 
nivel pasado lo que nos dara la siguiente contraseña
password:MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

bandit3

Para esta nivel nos pedian acceder a un hidden file para 
eso ponemos ls lo que nos mostrara que hay una carpeta 
llamada "inhere".
Cuando nos metemos en la carpeta y hacemos ls vemos que no 
hay ningun archivo por lo que para ver los archivos ocultos
ponemos "ls -a" lo cual nos mostrara los archivos ocultos tras
sabes como este hacemos un cat y listo ya tenemos la 
contraseña para el siguiente nivel

password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

bandit4

Para este nivel me pedia que buscara la contraseña que se encuentra en un "only human-readable file", para esto de primeras he 
hecho un "ls" para ver lo que habia. Tras hacer esto vi que habia una carpeta llamada "inhere", me meti en esta carpeta hice 
otro "ls" y vi que habia muchas carpetas. Para averiguar cual era busque que era un "only human-readable file" y m epropuse a 
encontrar como solucionar este problema. Cuando termine de investigar me dispuse a poner en practica lo que encontre, para ver lo
que tenia cada carpeta puse lo siguiente "file -- *" con este comando pude ver al fin lo que habia en cada carpeta y vi que en 
la carpeta "file07" habia un archivo ascci.txt por lo que abri este poniendo lo siguiente "cat ./-file07"

password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

bandit5

Para este nivel se nos pide que la carpeta donde la contraseña se encuentra tiene las siguiente caracteristicas human-readable,
1033 bytes in size y not executable. Para esto de primeras nos metemos en la carpeta inhere donde encontraremos un monton de 
carpetas, despues de ver un monton de carpetas pondremos esto "find . -type f -size 1033c ! -executable | xargs file | grep tex" 
tras poner esto la terminal nos pone esto "./maybehere07/.file2: ASCII text, with very long lines (1000)" por lo que pondremos 
lo siguiente para abrir el archivo "cat ./maybehere07/.file2" dandonos con esto la contraseña del siguiente nivel

password:HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

bandit6

password:
