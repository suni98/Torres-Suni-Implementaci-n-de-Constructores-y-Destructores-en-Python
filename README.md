# Torres-Suni-Implementaci-n-de-Constructores-y-Destructores-en-Python
class Archivo:
    def __init__(self, nombre):
        self.nombre = nombre
        self.archivo = open(nombre, 'r')
        print(f'Archivo {self.nombre} abierto.')

    def leer_contenido(self):
        contenido = self.archivo.read()
        print(f'Contenido del archivo {self.nombre}:')
        print(contenido)

    def __del__(self):
        if hasattr(self, 'archivo') and self.archivo:
            self.archivo.close()
            print(f'Archivo {self.nombre} cerrado.')

# Ejemplo de uso
if __name__ == "__main__":
    # Creamos una instancia de Archivo
    archivo = Archivo('ejemplo.txt')
    
    # Hacemos algo con el archivo
    archivo.leer_contenido()
    
    # El destructor se llamará al salir del bloque
