# Examen
from tkinter import*
import turtle
import math
t=turtle.Pen()

def ShowChoice():
    print (v.get())
    boton1()
    
def boton1():
    a=0
    tamaño=0
    print('Bienvenido ingrese el numero de lados')
    a=int(input())
    print('ingrese el tamaño del lado')
    tamaño=int(input())
    if a<=5 and a>2:
        if a==4:
            angulo=(a-2)*180/a
            perimetro=4*tamaño
            area=tamaño*tamaño
            print('El perimetro es igual a ...........',perimetro)
            print('El area es.............',area)
        elif a==3:
            v=math.sqrt(3)
            perimetro=4*3
            area=(v/4)*tamaño
            angulo=120
            print('El perimetro es igual a ...........',perimetro)
            print('El area es.............',area)
        else:
            angulo=72
            radio=int(input('El poligono a resolver necesita el radio como dato'))
            perimetro=5*tamaño
            area=(perimetro*radio)/2
            print('El perimetro es igual a ...........',perimetro)
            print('El area es.............',area)

        t.reset()
        for x in range(0,a):
            t.forward(tamaño)
            t.left(angulo)
        turtle.getscreen()._root.mainloop()
    else:
        print("numero de lados ingresado no es valido")
 


root = Tk()
v = IntVar()
v.set(1)
languages = [("Ejercicio 1",1),("Ejercicio 2",2)]
Label(root, text="""Escoja un programa para :""",
    justify = CENTER,padx = 20).pack()
for txt, val in languages:
    Radiobutton(root, text=txt,
                indicatoron =0,
                width = 20,
                padx =20,
                variable=v,
                command=ShowChoice,
                value=val).pack(anchor=W)
mainloop()
