//this is the source file pro.txt

copy start 10000
FIRST sl RETADR 
CLOOP jsub RDREC 
 la LENGTH 
 comp ZERO 
 J CLOOP 
ENDFIL la EOF 
 sa BUFFER
 la THREE
 rsub 
 sa LENGTH
 jsub WRREC
 clear p
 =ldl RETADR 
 byt c'eof'
 comp a,p
THREE word 3
ZERO word 0
RETADR resw 1
LENGTH resw 1
BUFFER resb 4096 
record lx ZERO 
 la ZERO 
RLOOP td INPUT 
 jeq RLOOP 
 rd INPUT
 byt c'test' 
 comp ZERO
 jeq EXIT 
 sch BUFFER,X
 tr MAXLEN
 jtl RLOOP
EXIT sx LENGTH
INPUT byt x'f1'
MAXLEN word 5
WRREC lx ZERO
WLOOP td OUTPUT
 jeq WLOOP
 comp a,t
 lch BUFFER,X
 wd OUTPUT 
 tr LENGTH 
 jtl WLOOP
 end copy
 
 //This is object file prog2.txt
 
 
la aa
sa a1     
byt a2                                 
tixr a3                                   
comp a4
add a5
sub a6
ls a7                                      
jl a8                                       
lx a9                
lt ab                
jsub ac
tr ad               
sl ae                 
jeq af              
ldl b0
td b1
rd b2
lch b3            
sch b4 
clear b5
ldt b6
eof 43454e
j b7
rsub b8
jtl b9
sx ba
registers 0
a 1         
t 2        
y 3         
g 4         
h 5         
i 6         
p 7         
pc 8 
sw 9
