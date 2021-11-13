# lab-01-insercao-lista-duplamente-encadeada-matheusscamargo
lab-01-insercao-lista-duplamente-encadeada-matheusscamargo created by GitHub Classroom
def main():
    lista = Lista()

    lista.append(Node(10)) 
    lista.add(Node(15)) 
    print(lista)

    lista.add(Node(100)) 
    lista.append(Node(20)) 

    lista.append(Node(30)) 
    lista.append(Node(40)) 
    lista.append(Node(50)) 
    print(lista)

    lista.add(Node(99)) 
    print(lista)


class Node:

    def __init__(self, x):
        self.value = x
        self.next = None
        self.prev = None


class Lista:

    def __init__(self):
        self.init = None
        self.tail = None

    def append(self, node):
        """
        Método para inserir um elemento no final
        """

        if self.init is None:
            self.init = node
            self.tail = node
            return

        node.prev = self.tail
        self.tail.next = node
        self.tail = node        


    def add(self, node):
        """
        Método para inserir um elemento sempre no inicio da lista
        """

        if self.init is None:
            self.init = node
            self.tail = node
            return

        node.next = self.init
        self.init = node


    def __str__(self):
        str_aux = ""
        node_aux = self.init

        while node_aux is not None:
            str_aux += str(node_aux.value) + " <=> "
            node_aux = node_aux.next

        str_aux = str_aux[:-5]

        return str_aux

if __name__ == '__main__':
    main()
