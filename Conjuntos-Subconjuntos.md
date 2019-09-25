#Programa que muestre todos los subconjuntos de tamaño n de un conjunto m
class Conjuntos():

    __m = ['A','B','C,','D']
    __n = int
    __c = 1


    def __init__(self,  n):
        self.__n = n

    def SubConjuntos(self):

        for a in range (0, len(self.__m)):
            for b in range (self.__c, len(self.__m)):
                print  (a, self.__m[a], self.__m[b])
            self.__c = self.__c + self.__n - 1



def main():
    Obj = Conjuntos(2)
    Obj.SubConjuntos()

if __name__ == '__main__':
    main()
