# -*- coding: utf-8 -*-
"""
Created on Thu Jul  9 22:45:21 2020

@author: die_a
"""


import random
#####crear tablero···································
import os
import sys
import time
from pygame import mixer

def limpiar():
    if os.name == "posix":
        os.system ("clear")
    elif os.name == "ce" or os.name == "nt" or os.name == "dos":
        os.system ("cls")
       
        
    
def dado_B():
    
    x=random.randint(1,6)
    #x=int(input("ingrese el valor del dado B"))
    mixer.init()
    mixer.music.load('dados2.mp3')
    mixer.music.play()
    time.sleep(1)
    if x==1:
        dado1=  [[" __","__","_"],
                 ["| ", "  ", "  |"],
                 ["| ", " o ", " |"],
                 ["|_","__","__|"]]    
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste",x)
        input("presiona enter para continuar")
    elif x==2:
        dado1= [[" __","__","_"],
                 ["|o", "  ", "  |"],
                 ["| ", "   ", " |"],
                 ["|_","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste",x)
        input("presiona enter para continuar")
    elif x==3:
        dado1= [[" __","__","_"],
                 ["|o", "  ", "  |"],
                 ["| ", " o ", " |"],
                 ["|_","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste",x)
        input("presiona enter para continuar")
    elif x==4:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["| ", "   ", " |"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste",x)
        input("presiona enter para continuar")
    elif x==5:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["| ", " o ", " |"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste",x)
        input("presiona enter para continuar")
    else:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["|o", "   ", "o|"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste",x)
        input("presiona enter para continuar")
    limpiar()
    salir_fichaB(x)
def salir_fichaB(x):
    if x==5 and tablero[7][7]== " B1 |" and tablero[7][8]==" B2 |" and tablero[10][6]=="____|" and tablero[10][10]=="*****"and tablero[10][9]=="*****":
        tablero[10][6]=" B1 |"
        tablero[7][7]="     " 
        print("true")
        mostrar2()
    elif x==5 and tablero[7][7]== " B1 |"   and tablero[10][6]=="____|" and tablero[10][10]=="*****"and tablero[10][9]=="*****":
        tablero[10][6]=" B1 |"
        tablero[7][7]="     "
        mostrar2()
    elif x==5 and tablero[7][7]== " B1 |"   and tablero[10][6]==" B2 |" and tablero[10][10]=="*****"and tablero[10][9]=="*****":
        ubicacion_ficha2B(x)
    
    elif x==5 and tablero[7][7]== " B1 |" and tablero[10][6]==" A1 |" and  tablero[10][10]=="*****" and tablero[10][9]=="*****":
        comer1(10,6,7,7,1,1)
    elif x==5 and tablero[7][7]== " B1 |" and tablero[10][6]==" A2 |" and  tablero[10][10]=="*****" and tablero[10][9]=="*****":
        comer1(10,6,7,7,1,2)
    elif x==5 and tablero[7][7]== " B1 |"  and tablero[10][6]==" C1 |" and  tablero[10][10]=="*****" and tablero[10][9]=="*****":
        comer1(10,6,7,7,1,3)
    elif x==5 and tablero[7][7]== " B1 |"  and tablero[10][6]==" C2 |" and  tablero[10][10]=="*****" and tablero[10][9]=="*****":
        comer1(10,6,7,7,1,4)    
    elif x!=5 and tablero[7][7]== " B1 |" and tablero[7][8]!=" B2 |"and  tablero[10][10]=="*****"and tablero[10][9]=="*****":
        ubicacion_ficha2B(x)    
        
    elif x==5 and tablero[7][7]!= " B1 |"and tablero[7][8]==" B2 |" and tablero[10][6]== "____|" and  tablero[10][10]=="*****" and tablero[10][9]=="*****":
        tablero[10][6]=" B2 |"
        tablero[7][8]="     "
        mostrar2()
    elif x==5 and tablero[7][8]==" B2 |" and tablero[10][6]== " B1 |"and  tablero[10][10]=="*****"and tablero[10][9]=="*****":
        ubicacion_ficha1B(x)
        
    elif x==5 and tablero[7][7]!= " B1 |" and tablero[7][8]==" B2 |" and tablero[10][6]== " A1 |" and tablero[10][10]=="*****"and tablero[10][9]=="*****":   
        comer1(10,6,7,8,2,1)
    elif x==5 and tablero[7][7]!= " B1 |" and tablero[7][8]==" B2 |" and tablero[10][6]== " A2 |" and  tablero[10][10]=="*****"and tablero[10][9]=="*****":
        comer1(10,6,7,8,2,2)
   
    elif x==5 and tablero[7][7]!= " B1 |" and tablero[7][8]==" B2 |" and tablero[10][6]== " C1 |" and tablero[10][10]=="*****"and tablero[10][9]=="*****":
        comer1(10,6,7,8,2,3)
        
    elif x==5 and tablero[7][7]!= " B1 |" and tablero[7][8]==" B2 |" and tablero[10][6]== " C2 |" and tablero[10][10]=="*****"and tablero[10][9]=="*****":
        comer1(10,6,7,8,2,4)
    elif x!=5 and tablero[7][7]!=" B1 |" and tablero[7][8]==" B2 |"and  tablero[10][10]=="*****"and tablero[10][9]=="*****":
        
        ubicacion_ficha1B(x)  
    elif x==5 and tablero[7][7]!= " B1 |" and tablero[7][8]!=" B2 |"and  tablero[10][10]=="*****"and tablero[10][9]=="*****":
        
        seleccionar_fichaB(x)
    
    elif x!=5 and tablero[7][7]!= " B1 |" and tablero[7][8]!=" B2 |"and  tablero[10][10]=="*****"and tablero[10][9]=="*****":
       
        seleccionar_fichaB(x)
    elif x!=5 and tablero[7][7]!= " B1 |" and tablero[7][8]==" A2 |"and  tablero[10][10]=="*****"and tablero[10][9]=="*****":     
        ubicacion_ficha1B(x)
        
    elif x==5 and tablero[7][8]==" B2 |" and tablero[10][6]=="____|" and tablero[10][10]=="1****":
        tablero[10][6]=" B2 |"
        tablero[7][8]="     "
        mostrar2()
    elif x==5 and tablero[7][8]==" B2 |" and tablero[10][6]==" A1 |" and tablero[10][10]=="1****":
        comer1(10,6,7,8,2,1)
    elif x==5 and tablero[7][8]==" B2 |" and tablero[10][6]==" A2 |" and tablero[10][10]=="1****":
        comer1(10,6,7,8,2,2)
    elif x==5 and tablero[7][8]==" B2 |" and tablero[10][6]==" C1 |" and tablero[10][10]=="1****":
        comer1(10,6,7,8,2,3)
    elif x==5 and tablero[7][8]==" B2 |" and tablero[10][6]==" C1 |" and tablero[10][10]=="1****":
        comer1(10,6,7,8,2,4)
    elif x!=5 and tablero[7][8]==" B2 |" and tablero[10][10]=="1****":
        mostrar2()
    elif x!=5 and tablero[7][8]!=" B2 |" and tablero[10][10]=="1****":
        ubicacion_ficha2B(x)
    elif x==5 and tablero[7][8]!=" B2 |" and tablero[10][10]=="1****":
        ubicacion_ficha2B(x)
    elif x==5 and tablero[7][7]==" B1 |" and tablero[10][6]=="____|" and tablero[10][9]=="2****":
        tablero[10][6]=" B1 |"
        tablero[7][7]="     "
        mostrar2()
    elif x==5 and tablero[7][7]==" B1 |" and tablero[10][6]==" A1 |" and tablero[10][9]=="2****":
        comer1(10,6,7,7,1,1)
    elif x==5 and tablero[7][7]==" B1 |" and tablero[10][6]==" A2 |" and tablero[10][9]=="2****":
        comer1(10,6,7,7,1,2)
    elif x==5 and tablero[7][7]==" B1 |" and tablero[10][6]==" C1 |" and tablero[10][9]=="2****":
        comer1(10,6,7,7,1,3)
    elif x==5 and tablero[7][7]==" B1 |" and tablero[10][6]==" C2 |" and tablero[10][9]=="2****":
        comer1(10,6,7,7,1,4)
    elif x!=5 and tablero[7][7]==" B1 |"  and tablero[10][9]=="2****":
        mostrar2()
    elif x!=5 and tablero[7][7]!=" B1 |"  and tablero[10][9]=="2****":
        ubicacion_ficha1B(x)
    elif x==5 and tablero[7][7]!=" B1 |"  and tablero[10][9]=="2****":
        ubicacion_ficha1B(x)    
    else:
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()  
        print("x es dierente de 5")
        
def seleccionar_fichaB(x):
    mostrar2()
    print("sacaste",x)
    print("seleciona que ficha quieres mover")
    f1=False
    while f1==False:
        f=input("si quieres mover la ficha B1 presiona 1, sino presiona 2")
        if f=="1":
            f1=True
            ubicacion_ficha1B(x)
            
        elif f=="2":
            ubicacion_ficha2B(x)
            f1=True
        else:
            print("no tienes esta ficha")
            f1=False
            limpiar()
            mostrar2()
           
    

    
def ubicacion_ficha1B(x):
    a=0
    b=0
    f=1
    for i in range(11):
        for j in range(11):
           if tablero[i][j]==" B1 |":
               print("ubicacion es",i,j)
               a=i
               b=j
               break
           else:
               pass
    print(a,b)
    andar_B(x,a,b,f)
def ubicacion_ficha2B(x):
    a=0
    b=0
    f=2
    for i in range(11):
        for j in range(11):
           if tablero[i][j]==" B2 |":
               print("ubicacion es",i,j)
               a=i
               b=j
               break
           else:
               pass
 
    andar_B(x,a,b,f)
global tablero
def andar_B(p,x,v,f):
    print(p)
    matriz_jugador1=[[0 , 0, 0, 0,21,20,19, 0, 0, 0, 0],
                     [0 , 0, 0, 0,22, 0,18, 0, 0, 0, 0],
                     [0 , 0, 0, 0,23, 0,17, 0, 0, 0, 0],
                     [0 , 0, 0, 0,24, 0,16, 0, 0, 0, 0],
                     [29,28,27,26,25, 0,15,14,13,12,11],
                     [30, 0, 0, 0, 0,45, 0, 0, 0, 0,10],
                     [31,32,33,34,35,44, 5, 6, 7, 8, 9],
                     [0 , 0, 0, 0,36,43, 4, 0, 0, 0, 0],
                     [0 , 0, 0, 0,37,42, 3, 0, 0, 0, 0],
                     [0 , 0, 0 ,0,38,41, 2, 0, 0, 0, 0],
                     [0 , 0 ,0, 0,39,40, 1, 0, 0, 0, 0]]
    k=x
    t=v

    y=matriz_jugador1[x][v]
    #pasos=p
    print(y)
    contador=0
    u=0
    while contador<p:
        if y==matriz_jugador1[0][4] or y==matriz_jugador1[1][4] or y==matriz_jugador1[2][4] or y==matriz_jugador1[3][4]:
            y=matriz_jugador1[x+1][v]
            contador=contador+1
            x=x+1
           
        elif y==matriz_jugador1[4][4] or y==matriz_jugador1[4][3] or y==matriz_jugador1[4][2] or y==matriz_jugador1[4][1]:
            y=matriz_jugador1[x][v-1]
            contador=contador+1
            v=v-1

        elif y==matriz_jugador1[4][0] or y==matriz_jugador1[5][0] :
            y=matriz_jugador1[x+1][v]
            contador=contador+1
            x=x+1
            
        elif y==matriz_jugador1[6][0] or y==matriz_jugador1[6][1] or y==matriz_jugador1[6][2] or y==matriz_jugador1[6][3]:
            y=matriz_jugador1[x][v+1]
            contador=contador+1
            v=v+1
           
        elif y==matriz_jugador1[6][4] or y==matriz_jugador1[7][4] or y==matriz_jugador1[8][4] or y==matriz_jugador1[9][4]:
            y=matriz_jugador1[x+1][v]
            contador=contador+1
            x=x+1
            
        elif y==matriz_jugador1[10][4]  :
            y=matriz_jugador1[x][v+1]
            contador=contador+1
            v=v+1
           
        elif y==matriz_jugador1[10][6] or y==matriz_jugador1[9][6] or y==matriz_jugador1[8][6]or y==matriz_jugador1[7][6] :
            y=matriz_jugador1[x-1][v]
            contador=contador+1
            x=x-1
           
        elif y==matriz_jugador1[6][6] or y==matriz_jugador1[6][7] or y==matriz_jugador1[6][8] or y==matriz_jugador1[6][9]:
            y=matriz_jugador1[x][v+1]
            contador=contador+1
            v=v+1
            
        elif y==matriz_jugador1[6][10] or y==matriz_jugador1[5][10]  :
            y=matriz_jugador1[x-1][v]
            contador=contador+1
            x=x-1
            
        elif y==matriz_jugador1[4][10] or y==matriz_jugador1[4][9] or y==matriz_jugador1[4][8] or y==matriz_jugador1[4][7]:
            y=matriz_jugador1[x][v-1]
            contador=contador+1
            v=v-1
           
        elif y==matriz_jugador1[4][6] or y==matriz_jugador1[3][6] or y==matriz_jugador1[2][6]or y==matriz_jugador1[1][6] :
            y=matriz_jugador1[x-1][v]
            contador=contador+1
            x=x-1
            
        elif y==matriz_jugador1[0][6] or y==matriz_jugador1[0][5]:
            y=matriz_jugador1[x][v-1]
            contador=contador+1
            v=v-1
            
        elif y==matriz_jugador1[10][5] or y==matriz_jugador1[9][5] or y==matriz_jugador1[8][5] or y==matriz_jugador1[7][5]:
            y=matriz_jugador1[x-1][v]
            contador=contador+1
            x=x-1
            
        elif y==matriz_jugador1[6][5] and p==1 or p-contador==1:
            print("coronaste una ficha")
            tablero[k][t]="____|"
            u=1
            contador=7
            
            if f==1:
                tablero[10][10]="1****"
            else:
                tablero[10][9]="2****"
        elif y==matriz_jugador1[6][5] and p>1 or contador-p>1:
            g=p-contador-2
            y=matriz_jugador1[x+g][v]
            contador=7
            x=x+g
        else:
            print("algo anda mal")
            

         
    print("posicion final", x,v)
    if tablero[x][v]==" B2 |" and f==1:
        print("no puede estar en la misma posicion")
        seleccionar_fichaB(p)
    elif tablero[x][v]==" B1 |" and f==2:
        print("no puede estar en la misma posicion")
        seleccionar_fichaB(p)
    elif tablero[x][v]==" B1 |" and f==1:
        tablero [x][v]=" B1 |"
        mostrar2()
    elif tablero [x][v]==" B2 |" and f==2:
        tablero [x][v]=" B2 |"
        mostrar2()
        
    elif tablero[x][v]==" A1 |":
        print("te comiste una ficha")
        
        comer1(x,v,k,t,f,1)
    elif tablero[x][v]==" A2 |":
        print("te comiste una ficha")
        comer1(x,v,k,t,f,2)
    elif tablero[x][v]==" C1 |":
        print("te comiste una ficha")
        comer1(x,v,k,t,f,3)
    elif tablero[x][v]==" C2 |":
        print("te comiste una ficha")
        comer1(x,v,k,t,f,4)
    elif u==1:
        mixer.init()
        mixer.music.load('win.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    else:
    
        actualizar2(x,v,k,t,f)
      


def comer1(x,v,k,t,f,n):
    if f==1 and n==1:
        tablero[k][t]="____|"
        tablero[x][v]=" B1 |"
        tablero[3][0]=" A1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==1:
        tablero[k][t]="____|"
        tablero[x][v]=" B2 |"
        tablero[3][0]=" A1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==2:
        tablero[k][t]="____|"
        tablero[x][v]=" B1 |"
        tablero[3][1]=" A2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
       
    elif f==2 and n==2:
        tablero[k][t]="____|"
        tablero[x][v]=" B2 |"
        tablero[3][1]=" A2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==3:
        tablero[k][t]="____|"
        tablero[x][v]=" B1 |"
        tablero[7][0]=" C1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==4:
        tablero[k][t]="____|"
        tablero[x][v]=" B2 |"
        tablero[7][1]=" C2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==4:
        tablero[k][t]="____|"
        tablero[x][v]=" B1 |"
        tablero[7][1]=" C2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==3:
        tablero[k][t]="____|"
        tablero[x][v]=" B2 |"
        tablero[7][0]=" C1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    else:
        print("algo anda mal")
def mostrar2():
    limpiar()
    for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
    
def actualizar2(x,v,x0,v0,f):
    limpiar()
    if f==1:
        tablero[x0][v0]="____|"
        tablero[x][v]=" B1 |"
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
        print("movio ficha 1")
    else:
        tablero[x0][v0]="____|"
        tablero[x][v]=" B2 |"
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
        print("movio ficha 2")
global tablero

def dado():
   x=random.randint(1,6)
   #x=int(input("ingrese el valor del dado A"))
   mixer.init()
   mixer.music.load('dados2.mp3')
   mixer.music.play()
   time.sleep(1)
   if x==1:
        dado1=  [[" __","__","_"],
                 ["| ", "  ", "  |"],
                 ["| ", " o ", " |"],
                 ["|_","__","__|"]]    
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==2:
        dado1= [[" __","__","_"],
                 ["|o", "  ", "  |"],
                 ["| ", "   ", " |"],
                 ["|_","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==3:
        dado1= [[" __","__","_"],
                 ["|o", "  ", "  |"],
                 ["| ", " o ", " |"],
                 ["|_","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==4:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["| ", "   ", " |"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==5:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["| ", " o ", " |"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   else:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["|o", "   ", "o|"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
   
        print("sacaste", x)
        input("presiona enter para continuar")
   limpiar()
   salir_fichaA(x)
   
def salir_fichaA(x):
    
    if x==5 and tablero[3][0]== " A1 |" and tablero[3][1]==" A2 |" and tablero[0][4]=="____|"and tablero[0][0]=="*****"  and tablero[0][1]=="*****":
        tablero[0][4]=" A1 |"
        tablero[3][0]="     " 
        print("true")
        mostrar2()
    elif x==5 and tablero[3][0]== " A1 |"   and tablero[0][4]=="____|" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        tablero[0][4]=" A1 |"
        tablero[3][0]="     "
        mostrar2()
    elif x==5 and tablero[3][0]== " A1 |"   and tablero[0][4]==" A2 |" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        ubicacion_ficha2(x)
        
    elif x==5 and tablero[3][0]== " A1 |"  and tablero[0][4]==" B1 |" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,0,1,1)
    elif x==5 and tablero[3][0]== " A1 |"  and tablero[0][4]==" B2 |" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,0,1,2)
    elif x==5 and tablero[3][0]== " A1 |"  and tablero[0][4]==" C1 |" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,0,1,3)
    elif x==5 and tablero[3][0]== " A1 |"  and tablero[0][4]==" C2 |" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,0,1,4)
    elif x!=5 and tablero[3][0]== " A1 |"and tablero[3][1]!=" A2 |" and tablero[0][0]=="*****"  and tablero[0][1]=="*****":
        ubicacion_ficha2(x)
    elif x==5 and tablero[3][0]!= " A1 |"and tablero[3][1]==" A2 |"and tablero[0][4]== "____|"and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        tablero[0][4]=" A2 |"
        tablero[3][1]="     "
        mostrar2()
    elif x==5 and tablero[3][1]==" A2 |"and tablero[0][4]== " A1 |" and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        ubicacion_ficha1(x)
        
    elif x==5 and tablero[3][0]!= " A1 |" and tablero[3][1]==" A2 |" and tablero[0][4]== " B1 |"  and tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,1,2,1)
    elif x==5 and tablero[3][0]!= " A1 |" and tablero[3][1]==" A2 |" and tablero[0][4]== " B2 |"  and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,1,2,2)
    elif x==5 and tablero[3][0]!= " A1 |" and tablero[3][1]==" A2 |" and tablero[0][4]== " C1 |"  and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,1,2,3)
    elif x==5 and tablero[3][0]!= " A1 |" and tablero[3][1]==" A2 |" and tablero[0][4]== " C2 |"  and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        comer(0,4,3,1,2,4)
    elif x!=5 and tablero[3][0]!= " A1 |" and tablero[3][1]==" A2 |"and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        ubicacion_ficha1(x)
    elif x==5 and tablero[3][0]!= " A1 |" and tablero[3][1]!=" A2 |"and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        seleccionar_ficha(x)
    elif x!=5 and tablero[3][0]!= " A1 |" and tablero[3][1]!=" A2 |"and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        seleccionar_ficha(x)    
        
    elif x!=5 and tablero[3][0]!=" A1 |" and tablero[3][1]==" A2 |"and  tablero[0][0]=="*****"and tablero[0][1]=="*****":
        ubicacion_ficha1(x)
        
    elif x==5  and tablero[3][1]==" A2 |" and tablero[0][4]== "____|"  and  tablero[0][0]=="1****":
        tablero[0][4]=" A2 |"
        tablero[3][1]="     "
        mostrar2()
    elif x==5  and tablero[3][1]==" A2 |" and tablero[0][4]== " B1 |" and tablero[0][0]=="1****":
        comer(0,4,3,1,2,1)
    elif x==5  and tablero[3][1]==" A2 |" and tablero[0][4]== " B2 |" and tablero[0][0]=="1****":
        comer(0,4,3,1,2,2)
    elif x==5  and tablero[3][1]==" A2 |" and tablero[0][4]== " C1 |" and tablero[0][0]=="1****":
        comer(0,4,3,1,2,3)
    elif x==5  and tablero[3][1]==" A2 |" and tablero[0][4]== " C2 |" and tablero[0][0]=="1****":
        comer(0,4,3,1,2,4)
        
    elif x!=5  and tablero[3][1]==" A2 |"  and  tablero[0][0]=="1****":
         mostrar2()
    elif x!=5  and tablero[3][1]!=" A2 |"  and tablero[0][0]=="1****":
        ubicacion_ficha2(x)
    elif x==5  and tablero[3][1]!=" A2 |"  and  tablero[0][0]=="1****":
        ubicacion_ficha2(x)
       
    elif x==5  and tablero[3][0]==" A1 |" and tablero[0][4]== "____|"  and  tablero[0][1]=="2****":
        tablero[0][4]=" A1 |"
        tablero[3][0]="     "
        mostrar2()
    elif x==5  and tablero[3][0]==" A1 |" and tablero[0][4]== " B1 |"  and  tablero[0][1]=="2****":
        comer(0,4,3,0,1,1)
        
    elif x==5  and tablero[3][0]==" A1 |" and tablero[0][4]== " B2 |"  and  tablero[0][1]=="2****":
        comer(0,4,3,0,1,2)
    elif x==5  and tablero[3][0]==" A1 |" and tablero[0][4]== " C1 |"  and  tablero[0][1]=="2****":
        comer(0,4,3,0,1,3)
    elif x==5  and tablero[3][0]==" A1 |" and tablero[0][4]== " C2 |"  and  tablero[0][1]=="2****":
        comer(0,4,3,0,1,4)
    elif x!=5  and tablero[3][0]==" A1 |"  and  tablero[0][1]=="2****":
        mostrar2()
    elif x!=5  and tablero[3][0]!=" A1 |"  and  tablero[0][1]=="2****":
        ubicacion_ficha1(x)
    elif x==5  and tablero[3][0]!=" A1 |"  and  tablero[0][1]=="2****":
        ubicacion_ficha1(x)
    else:
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()  
        print("x es dierente de 5")
   
   
global tablero

def seleccionar_ficha(x):
    mostrar2()
    print("sacaste", x)
    print("seleciona que ficha quieres mover")
    f1=False
    while f1==False:
        f=input("si quieres mover la ficha A1 presiona 1, sino presiona 2")
        if f=="1":
            f1=True
            ubicacion_ficha1(x)
            
        elif f=="2":
            ubicacion_ficha2(x)
            f1=True
        else:
            print("no tienes esta ficha")
            f1=False
            limpiar()
            mostrar2()
    
def ubicacion_ficha1(x):
    a=0
    b=0
    f=1
    for i in range(11):
        for j in range(11):
           if tablero[i][j]==" A1 |":
               print("ubicacion es",i,j)
               a=i
               b=j
               break
           else:
               pass
    print(a,b)
    andar(x,a,b,f)
def ubicacion_ficha2(x):
    a=0
    b=0
    f=2
    for i in range(11):
        for j in range(11):
           if tablero[i][j]==" A2 |":
               print("ubicacion es",i,j)
               a=i
               b=j
               break
           else:
               pass
    
    andar(x,a,b,f)
global tablero
def andar(p,x,v,f):
   
    matriz_jugador1=[[0 , 0, 0, 0, 1,40,39, 0, 0, 0, 0],
                 [0 , 0, 0, 0, 2,41,38, 0, 0, 0, 0],
                 [0 , 0, 0, 0, 3,42,37, 0, 0, 0, 0],
                 [0 , 0, 0, 0, 4,43,36, 0, 0, 0, 0],
                 [9 , 8, 7, 6, 5,44,35,34,33,32,31],
                 [10, 0, 0, 0, 0,45, 0, 0, 0, 0,30],
                 [11,12,13,14,15, 0,25,26,27,28,29],
                 [0 , 0, 0, 0,16, 0,24, 0, 0, 0, 0],
                 [0 , 0, 0, 0,17, 0,23, 0, 0, 0, 0],
                 [0 , 0, 0 ,0,18, 0,22, 0, 0, 0, 0],
                 [0 , 0 ,0, 0,19,20,21, 0, 0, 0, 0]]
    k=x
    t=v
    u=0
    y=matriz_jugador1[x][v]
    #pasos=p
    
    contador=0
    while contador<p:
        if y==matriz_jugador1[0][4] or y==matriz_jugador1[1][4] or y==matriz_jugador1[2][4] or y==matriz_jugador1[3][4]:
            y=matriz_jugador1[x+1][v]
            
            contador=contador+1
            x=x+1
            
        elif y==matriz_jugador1[4][4] or y==matriz_jugador1[4][3] or y==matriz_jugador1[4][2] or y==matriz_jugador1[4][1]:
            y=matriz_jugador1[x][v-1]
           
            contador=contador+1
            v=v-1
        elif y==matriz_jugador1[4][0] or y==matriz_jugador1[5][0] :
            y=matriz_jugador1[x+1][v]
            
            contador=contador+1
            x=x+1
        elif y==matriz_jugador1[6][0] or y==matriz_jugador1[6][1] or y==matriz_jugador1[6][2] or y==matriz_jugador1[6][3]:
            y=matriz_jugador1[x][v+1]
           
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[6][4] or y==matriz_jugador1[7][4] or y==matriz_jugador1[8][4] or y==matriz_jugador1[9][4]:
            y=matriz_jugador1[x+1][v]
            
            contador=contador+1
            x=x+1
        elif y==matriz_jugador1[10][4] or y==matriz_jugador1[10][5] :
            y=matriz_jugador1[x][v+1]
            
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[10][6] or y==matriz_jugador1[9][6] or y==matriz_jugador1[8][6]or y==matriz_jugador1[7][6] :
            y=matriz_jugador1[x-1][v]
            
            contador=contador+1
            x=x-1
        elif y==matriz_jugador1[6][6] or y==matriz_jugador1[6][7] or y==matriz_jugador1[6][8] or y==matriz_jugador1[6][9]:
            y=matriz_jugador1[x][v+1]
            
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[6][10] or y==matriz_jugador1[5][10]  :
            y=matriz_jugador1[x-1][v]
           
            contador=contador+1
            x=x-1
        elif y==matriz_jugador1[4][10] or y==matriz_jugador1[4][9] or y==matriz_jugador1[4][8] or y==matriz_jugador1[4][7]:
            y=matriz_jugador1[x][v-1]
           
            contador=contador+1
            v=v-1
        elif y==matriz_jugador1[4][6] or y==matriz_jugador1[3][6] or y==matriz_jugador1[2][6]or y==matriz_jugador1[1][6] :
            y=matriz_jugador1[x-1][v]
            
            contador=contador+1
            x=x-1
        elif y==matriz_jugador1[0][6]:
            y=matriz_jugador1[x][v-1]
            
            contador=contador+1
            v=v-1
        elif y==matriz_jugador1[0][5] or y==matriz_jugador1[1][5] or y==matriz_jugador1[2][5] or y==matriz_jugador1[3][5]:
            y=matriz_jugador1[x+1][v]
           
            contador=contador+1
            x=x+1
        elif y==matriz_jugador1[4][5] and p==1 or p-contador==1:
            print("coronaste una ficha")
            tablero[k][t]="____|"
            u=1
            contador=7
            if f==1:
                tablero[0][0]="1****"
            else:
                tablero[0][1]="2****"
         
        elif y==matriz_jugador1[4][5] and p>1 or p-contador>1:
            g=p-contador
            y=matriz_jugador1[x-g][v]
            contador=7
            x=x-g+2
        else:
            contador=7

          
    print("posicion final", x,v)
    if tablero[x][v]==" A2 |" and f==1:
        print("no puede estar en la misma posicion")
        seleccionar_ficha(p)
    elif tablero [x][v]==" A1 |"and f==2:
        print("no puede estar en la misma posicion")
        seleccionar_ficha(p)
    
    elif tablero [x][v]==" A1 |" and f==1:
        tablero [x][v]=" A1 |"
    
    elif tablero [x][v]==" A2 |" and f==2:
        tablero [x][v]=" A2 |"
        mostrar2()
    elif tablero[x][v]==" B1 |":
        print("te comiste una ficha")
        comer(x,v,k,t,f,1)
    elif u==1:
        mixer.init()
        mixer.music.load('win.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)

    elif tablero[x][v]==" B2 |":
        print("te comiste una ficha")
        comer(x,v,k,t,f,2)    
    elif tablero[x][v]==" C1 |":
        print("te comiste una ficha")
        comer(x,v,k,t,f,3)
    elif tablero[x][v]==" C2 |":
        print("te comiste una ficha")
        comer(x,v,k,t,f,4)  
    else:
    
        actualizar1(x,v,k,t,f)

def comer(x,v,k,t,f,n):
    if f==1 and n==1:
        tablero[k][t]="____|"
        tablero[x][v]=" A1 |"
        tablero[7][7]=" B1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==1:
        tablero[k][t]="____|"
        tablero[x][v]=" A2 |"
        tablero[7][7]=" B1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==2:
        tablero[k][t]="____|"
        tablero[x][v]=" A1 |"
        tablero[7][8]=" B2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
       
    elif f==2 and n==2:
        tablero[k][t]="____|"
        tablero[x][v]=" A2 |"
        tablero[7][8]=" B2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==3:
        tablero[k][t]="____|"
        tablero[x][v]=" A1 |"
        tablero[7][0]=" C1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==4:
        tablero[k][t]="____|"
        tablero[x][v]=" A2 |"
        tablero[7][1]=" C2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==4:
        tablero[k][t]="____|"
        tablero[x][v]=" A1 |"
        tablero[7][1]=" C2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==3:
        tablero[k][t]="____|"
        tablero[x][v]=" A2 |"
        tablero[7][0]=" C1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    else:
        print("Algo anda mal")
        
def actualizar1(x,v,x0,v0,f):
    limpiar()
    if f==1:
        tablero[x0][v0]="____|"
        tablero[x][v]=" A1 |"
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
        print("movio ficha 1")
    else:
        tablero[x0][v0]="____|"
        tablero[x][v]=" A2 |"
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
        print("movio ficha 2")
global tablero

def dado_C():
   x=random.randint(1,6)
   #x=int(input("ingrese el valor del dado C"))
   mixer.init()
   mixer.music.load('dados2.mp3')
   mixer.music.play()
   time.sleep(1)
   if x==1:
        dado1=  [[" __","__","_"],
                 ["| ", "  ", "  |"],
                 ["| ", " o ", " |"],
                 ["|_","__","__|"]]    
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==2:
        dado1= [[" __","__","_"],
                 ["|o", "  ", "  |"],
                 ["| ", "   ", " |"],
                 ["|_","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==3:
        dado1= [[" __","__","_"],
                 ["|o", "  ", "  |"],
                 ["| ", " o ", " |"],
                 ["|_","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==4:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["| ", "   ", " |"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   elif x==5:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["| ", " o ", " |"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
        print("sacaste", x)
        input("presiona enter para continuar")
   else:
        dado1= [[" __","__","_"],
                 ["|o", "  ", " o|"],
                 ["|o", "   ", "o|"],
                 ["|o","__","_o|"]]
        for i in range (4):
            for j in range (3):
                print(dado1[i][j], end="")
            print()
   
        print("sacaste", x)
        input("presiona enter para continuar")
   limpiar()
   salir_fichaC(x)

def salir_fichaC(x):
    
    if x==5 and tablero[7][0]== " C1 |" and tablero[7][1]==" C2 |" and tablero[6][0]=="____|"and tablero[10][0]=="*****"  and tablero[10][1]=="*****":
        tablero[6][0]=" C1 |"
        tablero[7][0]="     " 
        mostrar2()
    elif x==5 and tablero[7][0]== " C1 |"   and tablero[6][0]=="____|" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        tablero[6][0]=" C1 |"
        tablero[7][0]="     "
        mostrar2()
    elif x==5 and tablero[7][0]== " C1 |"   and tablero[6][0]==" C2 |" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        ubicacion_ficha2C(x)
        
    elif x==5 and tablero[7][0]== " C1 |"  and tablero[6][0]==" B1 |" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,0,1,1)
    elif x==5 and tablero[7][0]== " C1 |"  and tablero[6][0]==" B2 |" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,0,1,2)
    elif x==5 and tablero[7][0]== " C1 |"  and tablero[6][0]==" A1 |" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,0,1,3)
    elif x==5 and tablero[7][0]== " C1 |"  and tablero[6][0]==" A2 |" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,0,1,4)
    elif x!=5 and tablero[7][0]== " C1 |"and tablero[7][1]!=" C2 |" and tablero[10][0]=="*****"  and tablero[10][1]=="*****":
        ubicacion_ficha2C(x)
    elif x==5 and tablero[7][0]!= " C1 |"and tablero[7][1]==" C2 |"and tablero[6][0]== "____|"and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        tablero[6][0]=" C2 |"
        tablero[7][1]="     "
        mostrar2()
    elif x==5 and tablero[7][1]==" C2 |"and tablero[6][0]== " C1 |" and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        ubicacion_ficha1C(x)
        
    elif x==5 and tablero[7][0]!= " C1 |" and tablero[7][1]==" C2 |" and tablero[6][0]== " B1 |"  and tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,1,2,1)
    elif x==5 and tablero[7][0]!= " C1 |" and tablero[7][1]==" C2 |" and tablero[6][0]== " B2 |"  and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,1,2,2)
    elif x==5 and tablero[7][0]!= " C1 |" and tablero[7][1]==" C2 |" and tablero[6][0]== " A1 |"  and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,1,2,3)
    elif x==5 and tablero[7][0]!= " C1 |" and tablero[7][1]==" C2 |" and tablero[6][0]== " A2 |"  and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        comer3(6,0,7,1,2,4)
    elif x!=5 and tablero[7][0]!= " C1 |" and tablero[7][1]==" C2 |"and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        ubicacion_ficha1C(x)
    elif x==5 and tablero[7][0]!= " C1 |" and tablero[7][1]!=" C2 |"and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        seleccionar_fichaC(x)
    elif x!=5 and tablero[7][0]!= " C1 |" and tablero[7][1]!=" C2 |"and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        seleccionar_fichaC(x)    
        
    elif x!=5 and tablero[7][0]!=" C1 |" and tablero[7][1]==" C2 |"and  tablero[10][0]=="*****"and tablero[10][1]=="*****":
        ubicacion_ficha1C(x)
        
    elif x==5  and tablero[7][1]==" C2 |" and tablero[6][0]== "____|"  and  tablero[10][0]=="1****":
        tablero[6][0]=" C2 |"
        tablero[7][1]="     "
        mostrar2()
    elif x==5  and tablero[7][1]==" C2 |" and tablero[6][0]== " B1 |" and tablero[10][0]=="1****":
        comer3(6,0,7,1,2,1)
    elif x==5  and tablero[7][1]==" C2 |" and tablero[6][0]== " B2 |" and tablero[10][0]=="1****":
        comer3(6,0,7,1,2,2)
    elif x==5  and tablero[7][1]==" C2 |" and tablero[6][0]== " A1 |" and tablero[10][0]=="1****":
        comer3(6,0,7,1,2,3)
    elif x==5  and tablero[7][1]==" C2 |" and tablero[6][0]== " A2 |" and tablero[10][0]=="1****":
        comer3(6,0,7,1,2,4)
        
    elif x!=5  and tablero[7][1]==" C2 |"  and  tablero[10][0]=="1****":
         mostrar2()
    elif x!=5  and tablero[7][1]!=" C2 |"  and tablero[10][0]=="1****":
        ubicacion_ficha2C(x)
    elif x==5  and tablero[7][1]!=" C2 |"  and  tablero[10][0]=="1****":
        ubicacion_ficha2C(x)
       
    elif x==5  and tablero[7][0]==" C1 |" and tablero[6][0]== "____|"  and  tablero[10][1]=="2****":
        tablero[6][0]=" C1 |"
        tablero[7][0]="     "
        mostrar2()
    elif x==5  and tablero[7][0]==" C1 |" and tablero[6][0]== " B1 |"  and  tablero[10][1]=="2****":
        comer3(6,0,7,0,1,1)
        
    elif x==5  and tablero[7][0]==" C1 |" and tablero[6][0]== " B2 |"  and  tablero[10][1]=="2****":
        comer3(6,0,7,0,1,2)
    elif x==5  and tablero[7][0]==" C1 |" and tablero[6][0]== " A1 |"  and  tablero[10][1]=="2****":
        comer3(6,0,7,0,1,3)
    elif x==5  and tablero[7][0]==" C1 |" and tablero[6][0]== " A2 |"  and  tablero[10][1]=="2****":
        comer3(6,0,7,0,1,4)
    elif x!=5  and tablero[7][0]==" C1 |"  and  tablero[10][1]=="2****":
        mostrar2()
    elif x!=5  and tablero[7][0]!=" C1 |"  and  tablero[10][1]=="2****":
        ubicacion_ficha1C(x)
    elif x==5  and tablero[7][0]!=" C1 |"  and  tablero[10][1]=="2****":
        ubicacion_ficha1C(x)
    else:
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()  
        print("x es dierente de 5")

def comer3(x,v,k,t,f,n):
    
    if f==1 and n==1:
        tablero[k][t]="____|"
        tablero[x][v]=" C1 |"
        tablero[7][7]=" B1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==1:
        tablero[k][t]="____|"
        tablero[x][v]=" C2 |"
        tablero[7][7]=" B1 |"
        mostrar2()
    elif f==1 and n==2:
        tablero[k][t]="____|"
        tablero[x][v]=" C1 |"
        tablero[7][8]=" B2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
       
    elif f==2 and n==2:
        tablero[k][t]="____|"
        tablero[x][v]=" C2 |"
        tablero[7][8]=" B2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==3:
        tablero[k][t]="____|"
        tablero[x][v]=" C1 |"
        tablero[3][0]=" A1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==4:
        tablero[k][t]="____|"
        tablero[x][v]=" C2 |"
        tablero[3][1]=" A2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==1 and n==4:
        tablero[k][t]="____|"
        tablero[x][v]=" C1 |"
        tablero[3][1]=" A2 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    elif f==2 and n==3:
        tablero[k][t]="____|"
        tablero[x][v]=" C2 |"
        tablero[3][0]=" A1 |"
        mixer.init()
        mixer.music.load('madera.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)
    else:
        print("Algo anda mal")
def seleccionar_fichaC(x):
    mostrar2()
    print("sacaste", x)
    print("seleciona que ficha quieres mover")
    f1=False
    while f1==False:
        f=input("si quieres mover la ficha C1 presiona 1, sino presiona 2")
        if f=="1":
            f1=True
            ubicacion_ficha1C(x)
            
        elif f=="2":
            ubicacion_ficha2C(x)
            f1=True
        else:
            print("no tienes esta ficha")
            f1=False
            limpiar()
            mostrar2()
    

   
def ubicacion_ficha1C(x):
    a=0
    b=0
    f=1
    for i in range(11):
        for j in range(11):
           if tablero[i][j]==" C1 |":
               print("ubicacion es",i,j)
               a=i
               b=j
               break
           else:
               pass
    print(a,b)
    andarC(x,a,b,f)
def ubicacion_ficha2C(x):
    a=0
    b=0
    f=2
    for i in range(11):
        for j in range(11):
           if tablero[i][j]==" C2 |":
               print("ubicacion es",i,j)
               a=i
               b=j
               break
           else:
               pass
    
    andarC(x,a,b,f)
    
def andarC(p,x,v,f):
   
    matriz_jugador1=[[0 , 0, 0, 0,31,30,29, 0, 0, 0, 0],
                     [0 , 0, 0, 0,32, 0,28, 0, 0, 0, 0],
                     [0 , 0, 0, 0,33, 0,27, 0, 0, 0, 0],
                     [0 , 0, 0, 0,34, 0,26, 0, 0, 0, 0],
                     [39,38,37,36,35, 0,25,24,23,22,21],
                     [40,41,42,43,44,45, 0, 0, 0, 0,20],
                     [ 1, 2, 3, 4, 5, 0,15,16,17,18,19],
                     [0 , 0, 0, 0, 6, 0,14, 0, 0, 0, 0],
                     [0 , 0, 0, 0, 7, 0,13, 0, 0, 0, 0],
                     [0 , 0, 0 ,0, 8, 0,12, 0, 0, 0, 0],
                     [0 , 0 ,0, 0, 9,10,11, 0, 0, 0, 0]]
    k=x
    t=v
    u=0
    y=matriz_jugador1[x][v]
    #pasos=p
    
    contador=0
    while contador<p:
        if y==matriz_jugador1[0][4] or y==matriz_jugador1[1][4] or y==matriz_jugador1[2][4] or y==matriz_jugador1[3][4]:
            y=matriz_jugador1[x+1][v]
            
            contador=contador+1
            x=x+1
            
        elif y==matriz_jugador1[4][4] or y==matriz_jugador1[4][3] or y==matriz_jugador1[4][2] or y==matriz_jugador1[4][1]:
            y=matriz_jugador1[x][v-1]
           
            contador=contador+1
            v=v-1
        elif y==matriz_jugador1[4][0]  :
            y=matriz_jugador1[x+1][v]
            
            contador=contador+1
            x=x+1
        elif y==matriz_jugador1[6][0] or y==matriz_jugador1[6][1] or y==matriz_jugador1[6][2] or y==matriz_jugador1[6][3]:
            y=matriz_jugador1[x][v+1]
           
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[6][4] or y==matriz_jugador1[7][4] or y==matriz_jugador1[8][4] or y==matriz_jugador1[9][4]:
            y=matriz_jugador1[x+1][v]
            
            contador=contador+1
            x=x+1
        elif y==matriz_jugador1[10][4] or y==matriz_jugador1[10][5] :
            y=matriz_jugador1[x][v+1]
            
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[10][6] or y==matriz_jugador1[9][6] or y==matriz_jugador1[8][6]or y==matriz_jugador1[7][6] :
            y=matriz_jugador1[x-1][v]
            
            contador=contador+1
            x=x-1
        elif y==matriz_jugador1[6][6] or y==matriz_jugador1[6][7] or y==matriz_jugador1[6][8] or y==matriz_jugador1[6][9]:
            y=matriz_jugador1[x][v+1]
            
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[6][10] or y==matriz_jugador1[5][10]  :
            y=matriz_jugador1[x-1][v]
           
            contador=contador+1
            x=x-1
        elif y==matriz_jugador1[4][10] or y==matriz_jugador1[4][9] or y==matriz_jugador1[4][8] or y==matriz_jugador1[4][7]:
            y=matriz_jugador1[x][v-1]
           
            contador=contador+1
            v=v-1
        elif y==matriz_jugador1[4][6] or y==matriz_jugador1[3][6] or y==matriz_jugador1[2][6]or y==matriz_jugador1[1][6] :
            y=matriz_jugador1[x-1][v]
            
            contador=contador+1
            x=x-1
        elif y==matriz_jugador1[0][6] or y==matriz_jugador1[0][5]:
            y=matriz_jugador1[x][v-1]
            
            contador=contador+1
            v=v-1
        elif y==matriz_jugador1[5][0] or y==matriz_jugador1[5][1] or y==matriz_jugador1[5][2] or y==matriz_jugador1[5][3]:
            y=matriz_jugador1[x][v+1]
           
            contador=contador+1
            v=v+1
        elif y==matriz_jugador1[5][4] and p==1 or p-contador==1:
            print("coronaste una ficha")
            tablero[k][t]="____|"
            u=1
            contador=7
            if f==1:
                tablero[10][0]="1****"
            else:
                tablero[10][1]="2****"
         
        elif y==matriz_jugador1[5][4] and p>1 or p-contador>1:
            g=p-contador
            y=matriz_jugador1[x][v-g]
            contador=7
            v=v-g+2
        else:
            contador=7
         
    print("posicion final", x,v)
    if tablero[x][v]==" C2 |" and f==1:
        print("no puede estar en la misma posicion")
        seleccionar_fichaC(p)
    elif tablero [x][v]==" C1 |"and f==2:
        print("no puede estar en la misma posicion")
        seleccionar_fichaC(p)
    
    elif tablero [x][v]==" C1 |" and f==1:
        tablero [x][v]=" C1 |"
    
    elif tablero [x][v]==" C2 |" and f==2:
        tablero [x][v]=" C2 |"
        mostrar2()
    elif tablero[x][v]==" B1 |":
        print("te comiste una ficha")
        comer3(x,v,k,t,f,1)
    elif u==1:
        mixer.init()
        mixer.music.load('win.mp3')
        mixer.music.play()
        mostrar2()
        time.sleep(1)

    elif tablero[x][v]==" B2 |":
        print("te comiste una ficha")
        comer3(x,v,k,t,f,2)    
    elif tablero[x][v]==" A1 |":
        print("te comiste una ficha")
        comer3(x,v,k,t,f,3)
    elif tablero[x][v]==" A2 |":
        print("te comiste una ficha")
        comer3(x,v,k,t,f,4)  
    else:
    
        actualizar3(x,v,k,t,f)
        
def actualizar3(x,v,x0,v0,f):
    limpiar()
    if f==1:
        tablero[x0][v0]="____|"
        tablero[x][v]=" C1 |"
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
        print("movio ficha 1")
    else:
        tablero[x0][v0]="____|"
        tablero[x][v]=" C2 |"
        for i in range (11):
            for j in range (11):
                print(tablero[i][j], end="")
            print()
        print("movio ficha 2")

def inicio():
    limpiar()
    j1=input("Ingresa el nombre del jugador 1: ")
    print()
    j2=input("Ingresa el nombre del jugador 2: ")

    for i in range (11):
        for j in range (11):
           print(tablero[i][j], end="")
        print()  
    q=0
    while q==0:
       
        if tablero[0][0]=="1****" and tablero[0][1]=="2****":
            print("Gano",j1, "Felicitaciones")
            mixer.init()
            mixer.music.load('ganar.mp3')
            mixer.music.play()
            time.sleep(1)
            input("Presiona enter para continuar")
            salir()
        elif tablero[10][10]=="1****" and tablero[10][9]=="2****":
            print("Gano",j2, "Felicitaciones")
            mixer.init()
            mixer.music.load('ganar.mp3')
            mixer.music.play()
            time.sleep(1)
            input("Presiona enter para continuar")
            salir()
        else:
            print("Juega ", j1)
            input("presione enter para continuar") 
            dado()
            mostrar2()
            print("Juega ", j2)
            input("presione enter para continuar")
            dado_B() 
  
    print("gracias")
global tablero

def inicio2():
    limpiar()
    j1=input("Ingresa el nombre del jugador 1: ")
    print()
    j2=input("Ingresa el nombre del jugador 2: ")
    print()
    j3=input("Ingresa el nombre del jugador 3: ")
    tablero[7][0]=" C1 |"
    tablero[7][1]=" C2 |"
    for i in range (11):
        for j in range (11):
           print(tablero[i][j], end="")
        print()  
    q=0
    while q==0:
       
        if tablero[0][0]=="1****" and tablero[0][1]=="2****":
            print("Gano",j1, "Felicitaciones")
            mixer.init()
            mixer.music.load('ganar.mp3')
            mixer.music.play()
            time.sleep(1)
            input("Presiona enter para continuar")
            salir()
        elif tablero[10][10]=="1****" and tablero[10][9]=="2****":
            print("Gano",j2, "Felicitaciones")
            mixer.init()
            mixer.music.load('ganar.mp3')
            mixer.music.play()
            time.sleep(1)
            input("Presiona enter para continuar")
            salir()
        elif tablero[10][0]=="1****" and tablero[10][1]=="2****":
            print("Gano",j3, "Felicitaciones")
            mixer.init()
            mixer.music.load('ganar.mp3')
            mixer.music.play()
            time.sleep(1)
            input("Presiona enter para continuar")
            salir()
        else:
            print("Juega ", j1)
            input("presione enter para continuar") 
            dado()
            mostrar2()
            print("Juega ", j3)
            input("presione enter para continuar") 
            dado_C()
            mostrar2()
            print("Juega ", j2)
            input("presione enter para continuar")
            dado_B() 
            
def jugadores():
    limpiar()
    print("¿Cuantos jugadores? ")
    print()
    print("Presiona 2 para dos jugadores")
    print()
    print("Prsiona 3 para 3 jugadores ")
    print()
    print("Presiona otra tecla para regresar al menu")
    a=input("Respuesta: ")
    if a=="2":
        inicio()
    elif a=="3":
        inicio2()
    else:
        limpiar()
        menu()
def salir():
    limpiar()
    print("Gracias por jugar")
    input("Presione enter para cerrar")
    sys.exit()
    
def instrucciones():
    print("Estas son las instrucciones del juego:")
    print()
    print("1)Solo hay un dado ")
    print("2)Siempre enpieza la ficha A y despues por derecha")
    print("3)Solo tiene un intento cada uno ")
    print("4)La ficha sale de la carcel si sale 5")
    print("5)Las fichas de la misma letra no pueden estar en la misma casilla ")
    print("6)Si caes en una casilla donde habia una ficha de otra letra, esta vuelve a la carcel")
    print("7)Al momento de la llegaba, la ficha debe caer exactamente, sino, los movimientos de mas comenzara a retroceder")
    print("8)El juego termina cuando un jugador corone sus dos fichas")
    print()
    input("Presiona enter para regresar al menu")
    limpiar()
    menu()
    
def menu():
    print("Bienvenido ")
    print()
    print("Presiona 1 si quieres jugar")
    print()
    print("Presiona 2 si quieres ver las instrucciones")
    print()
    print("Presiona otra tecla si quieres salir")
    a=input("Respuesta: ")
    if a=="1":
        jugadores()
    elif a=="2":
        instrucciones()
    else:
        salir()
    
tablero=     [["*****","*****","*****","*****","____|","____|","____|","*****","*****","*****","*****"],
              ["*****","*****","*****","*****","____|","____|","____|","*****","*****","*****","*****"],
              ["*****","*****","*****","*****","____|","____|","____|","*****","*****","*****","*****"],
              [" A1 |"," A2 |","*****","*****","____|","____|","____|","*****","*****","*****","*****"],
              ["____|","____|","____|","____|","____|","____|","____|","____|","____|","____|","____|"],
              ["____|","____|","____|","____|","____|","Meta ","____|","____|","____|","____|","____|"],
              ["____|","____|","____|","____|","____|","____|","____|","____|","____|","____|","____|"],
              ["*****","*****","*****","*****","____|","____|","____|"," B1 |"," B2 |","*****","*****"],
              ["*****","*****","*****","*****","____|","____|","____|","*****","*****","*****","*****"],
              ["*****","*****","*****","*****","____|","____|","____|","*****","*****","*****","*****"],
              ["*****","*****","*****","*****","____|","____|","____|","*****","*****","*****","*****"]]

menu()
