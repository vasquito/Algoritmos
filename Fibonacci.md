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

