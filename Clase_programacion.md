### Clase programación 


### Merge Sort
- FUe inventado por john von neumann en 1945
- un algoritmo muy eficiente basado en comparación, de hecho óptimo trabajo realizado: O(nlogn)
- Requiere una memoria adicional igual a n (número de datos) para trabajar.
- Es uno de los algoritmos llamados "divide y venceás", ya que explota la idea de dividir el probema mayor en problemas más pequeños, los cuales tardan menos en resolverse, para después usar esas soluciones para encontrar la solución del problema mayor 

Trabajo del merge sort
- Merge sort trabaja con una idea muy simple en tres pasos.
    - Divide el arreglo desordenado en dos partes.
    - Ordena cada una de las partes recursivamente (llamado merge sort)
    - Combina (merge) las partes resultantes ya ordenadas

- El método hace una copia del arreglo de entrada a, a unareglo auxiliar aux y luego combina(merge) de regreso al arreglo de entrada.
- Para ordenar el arreglo a[lo...hi], se divide en dos partes a[lo..mid] y a [mid+1,hi], se ordenan independientemente se mezclan (merge)




Algortimo de merge sort
~~~C++
int aux[n];

void sort (int a[], int lo, int hi)
{//ordenar a [lo..hi]
if (hi <= lo)retrurn;
int mid = lo + (hi - lo)/2;
sort(a,lo,mid); //ordenar la mitad izquierda
sort (a,mid+1,hi);// ordenar la mitad derecha
merge(,lo,mid,hi;)//merge las dos mitades
}

void merge(int a [], int lo, int mid, int hi)
{
    //merge a[lo..mid] con a [mid+1.hi]
    //copiar a[lo..hi] a aux[lo..hi]
    //merge de regreso en a [lo..hi]
}
~~~
 
 Proeso de merging y ejemplo 
 - La clave del algoritmo es un proceso de mezcla llamado merge, que toma dos arreglos ya ordenados para formar un solo arreglo ordenado.

 a[]  [E,E,G,M,R,A,C,E,R,T]
       k
Primero hace una copia del arreglo y lo pasa abajo 
      lo     mid mid+1   hi
aux[] [E,E,G,M,R|A,C,E,R,T]
       i         j

primero se compara el primero de la izquierda con el primero de la derecha, si es menor se coloca arriba, si no el de la derecha se coloca arriba y se va incrementando 
a[] [A]
     k
aux[] [E,E,G,M,R|A,C,E,R,T]
       i         j

hasta que queda
a[A,C,E,E,E,G,M,R,R,T]


### Quick sort
Fue inventado por el científico británico Sir Charles Antony "Tony" Richard Hoare (1934-2026), Premio turing 1980 en 1961
- probablmente es el algoritmo más utilizado
- Es un algoritmo del enfoque "divide y vencerás"
- Es sumamente eficiente en promedio: O(nlogn)

Trabaja de la siguiengte forma:
- Elegir un elemento de la lista de elementos a ordenar, al que lamaremos *pivote*.
- partición: resituar los demás elementos de la lista a cada lado del pivote, de manera que a un lado queden todos lo menores que el y del otro lado todos los mayores. En este momento, el pivote ocupa exactamente el lugar que corresponderá en la lista ordenada 
- La lista queda separada en 2 sublistas, una formada por los elementos a la izquierda y otra por los elementos a la derecha.
- repetir este proceso seleccionando otro pivote hasta que queden ordenados 

Proceso y ejemplo:
- Fase1: Repetir hasta que los apuntadores i y j se crucen:
    - mover i de izquierda a derecha mientras que a[i] < a [lo]
    - mover j de derecha a izquierda mientras que a[j] > a [lo]

Fase2: cuando los apuntadores se cruzan
Cambiar a[lo] con a [j]


### Apuntadores
Temas:
Administración de memoria 
apuntadores y referencias 

La memoria
- la memoria de l acomputadora es una colección de celdas que guardan datos en binario
- dichas celdas están colocadas en forma secuencial, una inmediatamente después de la otra
- cada una de las celdas tiene un "nombre" conocido como dirección
- Cada celda puede guardar un byte d einformación
- los idferentes tipos de variables utilizan diferentes cantidades de bytes (celdad) para ser almacenado:
    - Entero: normalmente 4 bytes en sistemas de 64 bytes (antes, con procesadores de menos de 16 bits usaban 2)
    - flotante: normalmente de 4 a 8 bytes (float y double)
    - char: normalmente 1 

Apuntadores
- un pointer en programación es un objeto o variable cuyo valor hace referencia o apunta a otro objeto almacenado en la memoria 
- se pede decir que un apuntaodr guarda una dirección de memoria  donde se almacena otro objeto
- fueron inventados por HAROLD LAWSON en 1964 para el lenguaje PL/1
ejemplo: a es un apuntador a la variable b que contiene un 56![ejemplo_apuntador](<Captura de pantalla 2026-10-13 123430.png>)

En C++
Los apuntadores se declaran igual que cualquier variable, soo colocando un * antes dde la variable o después del tipo para indicar que es un apuntador 

Los apuntadores siempre guardan direcciones 
- el tipo en este caso, indica el tipo de variable al que apunta, es decir, ha apuntadores a enteros, a flotantes, a objetos etc. 

Ejemplo:
del anterior si a es entera la declaración es: 
~~~C++
int b = 56;
int * a = &b; // & da la dirección de la variable 
~~~
Contenido del objeto al que apunta
- en realidad cualquier apuntador contiene ( apunta a ) la dirección de memoria donde se encuentra el inicio del objeto (recordemos que un objeto puede ocupar varios bytes dependiendo de su tipo)

- para hacer referencia a una parte especial del objeto se usan offsets, cuyo valor depende del tipo de variable al que se tiene que hacer referencia 
- estos offsets se indican generalmente por medio de un punto (.) o una flecha (->) dependiendo del lenguaje
- cuando se crea un objeto (sobre un apuntador en c++) con la instrucción *new* y el constructor, el sistema aparta todo el espacio que requiere y regresa el apuntaodr al inicio de dicho objeto (se le debe dar la clase del objeto para que sepa cuánto espacio apartar)
- en otras palabras, un apuntaodr guarda una dircción de memoria donde inicia un objeto 
Ejemplo 
~~~C++
#include <iostream>
using namespace std;

class Rect{
public: 
    int base = 0;
    int altura = 0;

    int getBase(){
        return base;
    }
   
    void setBase(int b){
        base = b;
    }
   
    int getAltura(){
        return altura;
    }
    
    void setAltura(int h){
        altura = h;
    }
};

int main(){
    Rect a;
    Rect *b;

    a.altura = 9;
    cout << "Altura del objeto a: " << a.getAltura() << endl;
    
    b = new Rect();
    b -> base = 3;
    cout << "Base del objeto b: " << b -> getBase() << endl;

    cout << "Dirección de memoria del objeto b: " << b << endl;
    return 0;
}
~~~
Paso de parámetros 
- los parámetros de un método o función, normalmnete, se pueden pasar por referencia o valor.
- cuando se pasan por referencia, lo que realmente se está pasando es la dirección de la variable, de tal fora que, si se modifica su valor en el métiodo, se cambia también afuera 
- cuando se pasan por valor, lo que realmente se está padando es una copia de la variable, de tal forma que su cambio de valor dentro del procedimiento o afecta a la variab,e originalñ.
 - C++ permite pasar parámetros de ambas formas: 
    - cuando es por referencia se indica con un & en la declaración del método.
- Java pasa *todos* sus parámetros por valor:
    - SI SON OBJETOS, PASA UNA COPIA DEL APUNTADOR A DICHO OBJETO 

---
Admiistración de la memoria 
- La administración de la memoria se refiere a la forma en la qe se asigna un espacio de memoria a todos los elementos que forman parte de un programa, para que éste pueda correr sin problema.
- Es importante conocer los conceptos generales de manejo de memoria por parte e los sistemas computacionales, pero también se debe tomar en cuenta que cada lenguaje de programación hace un manejo especídfico de la misma.
- en otras palabras, es ecesario estudiar la forma en la que lo hace el lenguaje que está usando (e.g. java)

Constructores
- método que se ejecuta automáticamnete cuando se crea un objeto



~~~c++
#include <iostream>
using namespace std;

void pasoValor(int d){
    cout << "valor: " << d << endl;
    d = 9;
    cout << "valor modificado: " << d << endl;
}

void pasoReferencia(int &d){
    cout << "valor: " << d << endl;
    d = 9;
    cout << "valor modificado: " << d << endl;
}


int main(){
   int e = 10;
   cout << "Valor Original: " << e << endl;
   pasoReferencia(e);
   cout << "Valor después de la función: " << e << endl;
    return 0;
}

~~~

Constructor de copia en c++
Este tipo de constructor se activa cuando al crear un objeto se inicializa con otro objeto de la misma clae 
- se invoca en tres situaciones:
- Complejo z1(1,3) // se inicializa con el constructor, sin memoria dinámica 
- Complejo z2 = z1 //z2 se inicializa con el constructor de copia 
- cuando se pasa un objeto por valor a una función 
- cuando la función devuelve un objeto 

- no es siemore necesario definir un constructor e copia, por defecto se realiza una copia miembro a miembro 
- sin embargo, cuando la clase tenga atributos (apuntadores) que represente memoria dinámica, buffer dinámico, sí debe definirse para realizar una copia egura, reservando memoria y copiando en esa memoria o buffer los elementos.
---
Apuntador nulo en c++
- hay valores muy comúnes para inicializar las varibles:
    - el 0 para una variable entera (int).
    - el 0.0 para una variable real (float).
    - el "(string o carácter nulo) para una variable cadena (string) o caráctwr (char)
- También existe un valor común para inicializar variables apuntador que es el apuntador nulo.
    - se hace referencia al apuntador nulo en c++ con l valor nullptr.
    también se heredó de C: NULL o 0, pero es mejor nullptr porque asegura estricta seguridad en el tipo de dato debido a que los otros son enteros.
- su uso es simple: <tipo> *p = nullptr;
---
vida de una variable

- La regla en trodos los lenguajes de programación dice que cuando se termina de ejecutar el bloque (función, instrucción o bloque) en dnde se declara una variable, la variable automáticamente deja de existir 
- cuando la variable deja de existir, también lo hace el espacio que el sistema normal le dio para guardar su valor
- sin embargo, si el espacio se asignó por medio del sistema para memoria dinámica (con la instucción new), el sistema normal mo puede eliminarlo y se tiene que hacer de otra forma

memory leak: cuando un apuntador se desaparece con su contenido ( o sea una dirección) el contenido nunca lo regresa entonces queda ahí flotando 


--- 
recolección de objetos en java
- en java, un objeto siempre debe estar referenciado por una variable.
    - en el momento en que un objeto deja de estar referenciado se activa una rutina de recolección de memoria, donde se puede decir que el objeto es liberado y la memoria puede ser reutilizada, ej: 
    - punto p = new Punto(2,3;)
    - cuando se hace p = null, provoca que el objeto p sea liberado automáticamnete.
- El propio sistema se encarga de recolectar los objetoos en desuso para aprovechar la memoria ocupada: 
    - para ello, hay un proceso que se activa periódicamente y toma los objetos que no están referenciados por ninguna variable.
    - El proceso lo realiza el método System.gc (garbage collection)

### Pila o stack
estructrura de datos lineal en la cual sus elementos pueden insertar y eliminARSE SÓLO POR UNO DE LOS EXTREMOS
- por lo tanto 


--- 
adt pila
Lo visto nteriormente es el concepto de la estructira de datos llamado pila 
este concepto nos permite diseñar un ADT pila 

---
Operaciones
Push y pop 
Push: método que recibe como parámeteo el valor que se desea insertar 
 - antes de insertar el elemento es necesario verificar que haya espacio disponible
 - 

 Pop: método que elimina un valor de la pila 

 ~~~c++
#include <iostream>
#define MAX 5
using namespace std;

class Pila{
    private: 
        int top = -1; //apunta al último elemento que entró a la pila
        int datos [MAX];
    
    public:
        void push (int dato) {
            if (top < MAX - 1) {
                top++;
                datos[top] = dato;
            } else {
                cout << "Error: Pila llena" << endl;
            }
        }

        void pop(){
            if (top==-1)
            cout << "Error Pila vacía\n";
            else 
            top--;
        }

        void imprimePila(){
            for (int i = 0; i <= top; i++)
            cout << datos[i] << " ";
        cout << endl;
        }
    };

    int main(){
        Pila miPila;
        miPila.push(5);
        miPila.imprimePila();
        miPila.push(3);
        miPila.imprimePila();
        miPila.push(7);
        miPila.imprimePila();
        miPila.push(9);
        miPila.imprimePila();
        miPila.push(1);
        miPila.imprimePila();
        miPila.push(4);
        miPila.imprimePila();
        miPila.pop();
        miPila.imprimePila();
        miPila.pop();
        miPila.imprimePila();
        miPila.pop();
        miPila.imprimePila();
        miPila.pop();
        miPila.imprimePila();
        miPila.pop();
        miPila.imprimePila();
        miPila.pop();
        miPila.imprimePila();
        return 0;
    }

 ~~~

 Expresioens aritméticas
 - las expresiones aritméticas se pueden manejar en 3 notaciones diferentes: 
    - infijo: los operadores van en medio de los operandos (e.g. a+b)
    - prefijo: los operadores van antes de los operaods (e.g +ab)
    - posfijo: los operadores van después de los operandos (e.g ab+)
    las notaciones pre y pos fijo tienen ventajas de que no requieren par´ntesis para escribirlas y no hace falta especificar presedencia de los operadores 

conversión para convertir de infijo a pos y prefijo
algoritmo infijo a posfijo (prefijo) //paréntesis significa prefijo

- agregar el operdador que se ejecuta al final a la derecha (izquierda)
- agregar su operando derecho (izquierdo) a la izquierda (derecha)
    - si es una variable o constante, agregarlo directamente
    - si es una expresi´n agregarla en posfijo (prefijo)
- agregando su operando izquierdo (derecho) a la izquierda (derecha)
    - si es una variable o constante, agregarlo directamente
    - si es una expresión, agregarla en posfijo