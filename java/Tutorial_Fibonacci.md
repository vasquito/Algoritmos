Analisis de un algoritmo de Fibonacci

Introduccion
 
La sucesion de Fibonacci

Fn 
--> 0 si n = 0 ;
--> 1 si n = 1 ;
--> Fn−1 + Fn−2 si n ≥ 2 .

Fue presentada en oriente por Leonardo de Pisa cerca del año 1202. Sin embargo, fue descubierta antes por matematicos hindues. 
Existen muchas propiedades y aplicaciones en teorıa de numeros juegos como tambien en computacion. 
A modo de ejemplo, estos numeros con ciertas restricciones son el peor caso delalgoritmo de Euclides -cuyo analisis es muy complicado-.

Comunmente en computacion cuando se presentan mecanismos para calcular un numero de Fibonacci se mencionan tres algoritmos. 
En primer lugar uno recursivo que sale de la definicioon, luego uno iterativo de orden n y por ultimo
otro recursivo que utiliza tecnicas de divide and conquer que es de orden log n.

Algorithm 1 fibonacci

Require: n ≥ 0
if n = 0 then
  return 0
else 
if n = 1 then
  return 1
else
  return fibonacci (n − 1) + fibonacci (n − 2)
end if


El objetivo aquı es analizar el primero y ver que su orden es exponencial. 
Para el analisis se utilizaran tecnicas de funciones generatrices ya que la metodologıa
es lo suficientemente general para analizar varias clases de algoritmos por lo que
este ejemplo puede servir como una breve introduccion.

a sucesión de Fibonacci
En ocasiones también conocida como secuencia de Fibonacci o incorrectamente como serie de Fibonacci, es en sí una sucesión matemática infinita. Consta de una serie de números naturales que se suman de a 2, a partir de 0 y 1. Básicamente, la sucesión de Fibonacci se realiza sumando siempre los últimos 2 números (Todos los números presentes en la sucesión se llaman números de Fibonacci) de la siguiente manera:

0,1,1,2,3,5,8,13,21,34...

Fácil, ¿no?

(0+1=1 / 1+1=2 / 1+2=3 / 2+3=5 / 3+5=8 / 5+8=13 / 8+13=21 / 13+21=34...)

Así sucesivamente, hasta el infinito. Por regla, la sucesión de Fibonacci se escribe así:

n = n-1 + n-2.

Recursividad
En palabras simples, la recursividad es cuando una función tiene la característica de poder llamarse a sí misma dentro de sus instrucciones; gracias a esto, podemos utilizar a nuestro favor la recursividad en lugar de la iteración para resolver determinados tipos de problemas.

Función Fibonacci recursiva
int fibonacci(int n)
{
    if (n>1){
       return fibonacci(n-1) + fibonacci(n-2);  //función recursiva
    }
    else if (n==1) {  // caso base
        return 1;
    }
    else if (n==0){  // caso base
        return 0;
    }
    else{ //error
        System.out.println("Debes ingresar un tamaño mayor o igual a 1");
        return -1; 
    }
}
La función nos devolverá el número correspondiente a la secuencia Fibonacci en la posición ‘n’, para obtener este número tiene que calcular toda la serie, haciendo recursividad hacia atrás hasta llegar al caso base, en este caso tenemos dos casos base, uno si es cero nos devolverá 0, y si es uno, nos devolverá 1, estos son los dos primeros números de la sucesión, luego viene la parte recursiva que es el llamado a la suma de la función fibonacci de los dos números anteriores, o mejor dicho la suma de las dos numeros anteriores al actual de la sucesión, en caso el número sea menor o igual a 0 la función nos indicará el error.    

Clase Fibonacci
Bien, ahora que ya tenemos nuestra función Fibonacci, vamos hacer de esta sucesión una clase para aprovechar al máximo el paradigma orientado a objetos que Java nos proporciona.

Una clase es una instancia abstracta que define un tipo de objeto especificando qué propiedades y operaciones disponibles va a tener. Una clase tiene atributos y métodos que pertenecen al objeto. Para nuestro ejemplo tendremos los siguientes atributos y métodos.

Atributos
public int tamaño;
public String nombre;
Nombre: Para cada objeto que tengamos le asignaremos un nombre específico para poder identificarla, este atributo será de tipo String que indica que es una cadena.

Tamaño: Cada sucesión tendrá un tamaño que indica cuántos elementos va a tener nuestra sucesión, este atributo es un entero.

Métodos
Tendremos dos constructores, el constructor vacío y otro predefinido por nosotros instanciando la clase pasandole valor a nuestros atributos.

public Fibonacci() { 
}

public Fibonacci(String nombre, int tamaño){
    this.nombre = nombre;
    this.tamaño = tamaño;
}
Además de un método que nos permite imprimir la sucesión  del tamaño que le especificamos, y que hace uso de la función fibonacci recursiva.

public void mostrarSerie(){
    System.out.println(this.nombre+" de tamaño "+this.tamaño+":");
    for (int i = 0; i < tamaño; i++) {
        System.out.print(fibonacci(i)+" ");
    }
    System.out.println();
}
Como cada clase agregamos sus respectivos métodos Getter and setter para los atributos de la clase, NetBeans nos proporciona una opción que genera estos métodos automáticamente.

public String getNombre() {
    return nombre;
}

public void setNombre(String nombre) {
    this.nombre = nombre;
}

public int getTamaño() {
    return tamaño;
}

public void setTamaño(int tamaño) {
    this.tamaño = tamaño;
}
Ya tenemos nuestra clase fibonacci lista, ahora desde el principal instanciamos esta clase en dos objetos de manera diferente, pero podemos observar que el resultado será el mismo.

Para el primer caso instanciamos la clase enviando los parámetros por el constructor y luego llamando a su método para mostrar la serie.

Fibonacci f1 = new Fibonacci("fibonacci 1",10); 
f1.mostrarSerie();
En el segundo caso instanciamos la clase con el constructor vacío, y luego enviando los parámetros por los métodos Setter, finalmente llamando a su método para mostrar la serie.

Fibonacci f2 = new Fibonacci();
f2.setNombre("fibonacci 2");
f2.setTamaño(10);
f2.mostrarSerie();
Como resultado obtendremos:

Puedes encontrar el código de este ejemplo en mi repositorio de GitHub: https://github.com/CarlosPlasencia/fibonacci
