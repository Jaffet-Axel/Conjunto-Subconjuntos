#Programa que muestre todos los subconjuntos de tamaño n letras de un conjunto de letras de tamaño m
#Ejemplo: de (A,B,C,D) obtener los subconjuntos de tamaño de 2 letras: (A,B) (A,C) (A,D) (B,C) (B,D) (C,D)
#Se estarán haciendo las pruebas con números enteros antes de hacerlas con letras
#Ejemplo: de (1,2,3,4) objener los subconjuntos de tamaño de 2 enteros: (1,2) (1,3) (1,4) (2,3) (2,4) (3,4)

class Subconjntos():
    #Conjunto       Es nuestro conjunto para sacar subconjuntos
    # t      Es el tamaño del conjunto
    # s      Es el tamaño de los subconjuntos que deseamos obtener
    # datos[]        Una lista temporal para almacenar las combinaciones una por una

    def SacarSubconjuntos(self, Conjunto, t, s):
        datos = [0] * s

        self.Combinacion(Conjunto, t, s, 0, datos, 0)


    def Combinacion(self, Conjunto, t, s, id, datos, i):
        if (id == s):
            for j in range(s):
                print(datos[j], end=" ")
            print()
            return

        if (i >= t):
            return

        datos[id] = Conjunto[i]
        self.Combinacion(Conjunto, t, s, id + 1,
                        datos, i + 1)



def main():
    Obj = Subconjntos()
    Obj.SacarSubconjuntos([4,3,2,1,6], len(Conjunto), 3)
if __name__ == "__main__":
    Conjunto = [1, 2, 3, 4, 5]
    r = 4
    n = len(Conjunto)
    main()
