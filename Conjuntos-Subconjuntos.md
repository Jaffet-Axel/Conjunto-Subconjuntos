class Subconjntos():

    #Conjunto[]     Es el conjunto de donde obtendremos nuestros subconjuntos
    #t      Es el tamaño del conjunto
    #s      Es el tamaño de los subconjuntos que deseamos obtener
    #id     Es el indice actual en datos[]
    #datos[]        Una lista temporal para almacenar las combinaciones una por una
    #i      índice del elemento actual en el conjunto


    def SacarSubconjuntos(self, Conjunto, t, s):
        datos = [0] * s         # Una matriz temporal para almacenar todas las combinaciones una por una

        self.Combinacion(Conjunto, t, s, 0, datos, 0)      # Imprimir todas las combinaciones usando la matriz temporal datos[]


    def Combinacion(self, Conjunto, t, s, id, datos, i):
        if (id == s):      #Si la combinación de subconjunto ya está lista(Si los subconjuntos que se piden son de tamaño 1), se imprime dato por dato.
            for j in range(s):
                print(datos[j], end=" ")
            print()
            return

        # Cuando no hay más elementos para poner en datos[]
        if (i >= t):
            return

        # id está incluido, poner siguiente en la siguiente ubicación
        datos[id] = Conjunto[i]
        self.Combinacion(Conjunto, t, s, id + 1,
                        datos, i + 1)

        # id está excluido, se reemplazó con el siguiente (tenga en cuenta que se pasa i + 1, pero el índice no cambia)
        self.Combinacion(Conjunto, t, s, id,
                        datos, i + 1)


def main():
    Obj = Subconjntos()
    Obj.SacarSubconjuntos(Conjunto, len(Conjunto), 2)
if __name__ == "__main__":
    Conjunto = ["A", "B", "C", "D"]
    t = len(Conjunto)
    main()
