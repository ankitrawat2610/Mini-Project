//source file pro.txt

copy start 1000 
 sl #14 
 jsub @RETADR 
 la LENGTH 
 base LENGTH 
 comp @ZERO 
ENDFIL la THREE 
 sa BUFFER 
FIRST sa LENGTH 
CLOOP jsub WRREC 
 clear p
 rsub 
 =ldl @THREE 
 byt c'eof' 
 comp a,p 
THREE word 3 
RETADR resw 1 
LENGTH resb 1 
record lx ZERO 
 la ZERO 
 td INPUT 
 jeq RLOOP 
RLOOP rd INPUT 
 byt c'ABCD' 
 comp ZERO 
ZERO jeq EXIT 
 sch BUFFER 
 tr MAXLEN 
 jtl INPUT 
EXIT sx MAXLEN 
INPUT byt x'f1' 
MAXLEN word 5 
WRREC lx WLOOP 
WLOOP td OUTPUT 
 comp a,t 
 lch BUFFER 
BUFFER wd OUTPUT 
OUTPUT jtl OUTPUT 
 end copy
 
 
 // opcode prog2.txt
 
 
 la AA
sa A1     
byt A2                                 
tixr A3                                   
comp A4
add A5
sub A6
ls A7                                      
jl A8                                       
lx A9                
lt AB                
jsub AC
tr AD               
sl AE                 
jeq AF              
ldl BF
td B1
rd B2
lch B3            
sch B4 
clear B5
ldt B6
eof 43454E
J B7
rsub B8
jtl B9
sx BA
wd BB
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
