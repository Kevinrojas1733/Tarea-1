

**2.1 Declaración de clases: atributos, métodos, encapsulamiento**

las clases y las estructuras son los constructores mas básicos que hay , básicamente lo que hacen es encapsular un conjunto de datos que va a almacenar un objeto cualquiera , en ellos se encuentra los métodos, propiedades y todos los eventos que contienen.

La declaración de clase se utiliza para crear objetos al momento de ejecutarse el programa, en estas clases se pueden crear diferentes objetos y que cada objeto tenga sus características específicas.
Cada que es creado un objeto, se le da una referencia única en la memoria a la cual se accede cuando son solicitados.
Cuando la referencia del objeto se le asigna a una variable mas esta tambien cambia ya que estas alterando el dato y hacen referencia al mismo.

La estructura es otro tipo de valor, el cual es como un copia porque la primera es la que tiene los datos reales de ella asi que son datos independientes , un cambio en una no afectará a la otra.
los métodos son las partes del código que contienen las instrucciones de lo que se realizará en el programa.
El encapsulamiento es lo que decide hasta que punto otros pueden manipular el programa.
La herencia sirve para pasar los valores como parámetros para así poder utilizarse en los métodos.

la encapsulación se dice que es como el primer pilar o principio de la programación orientada a objetos. esto es ya que segun este "pilar" tu debes decidir hasta que punto pueden acceder en cuestion de moverle al programa o cosas asi tu usuarios , no se prevé el uso de los métodos y las variables fuera de la clase, o el ensamblado puede ocultarse para limitar el potencial de los errores de codificación o de los ataques malintencionados.

Todos los métodos, campos, constantes, propiedades y eventos deben declararse dentro de un tipo; se les denomina miembros del tipo.
Las clases y las estructuras pueden heredar varias interfaces. Heredar de una interfaz significa que el tipo implementa todos los métodos definidos en la interfaz Las clases y estructuras pueden definirse con uno o varios parámetros de tipo. El código de cliente proporciona el tipo cuando crea una instancia del tipo.  Las clases (pero no las estructuras) pueden declararse como static. Una clase estática puede contener solo miembros estáticos y no se puede crear una instancia de ellos con la palabra clave new
Una clase o estructura se puede anidar dentro de otra clase o estructura. 
Puede definir parte de una clase, estructura o método en un archivo de código y otra parte en un archivo de código independiente.
Se puede crear instancias de objetos o de clases , sin llamar de forma explícita a su constructor. En situaciones donde no es conveniente o necesario crear una clase con nombre. 
Puede "extender" una clase sin crear una clase derivada mediante la creación de un tipo independiente cuyos métodos pueden llamarse como si pertenecieran al tipo original. Dentro de un método de clase o estructura, puede utilizar tipos implícitos para indicar al compilador que determine el tipo correcto en tiempo de compilación.

   **2.2 Instanciación de una clase.**
   new:new (operador)
Se usa para crear objetos e invocar constructores.

new (modificador)
Se usa para ocultar un miembro heredado de un miembro de clase base.

new (restricción)
Se usa para restringir tipos que pueden usarse como argumentos para un parámetro de tipo en una declaración genérica.




**2.3 Referencia al objeto actual.** 
La palabra clave this hace referencia a la instancia actual de la clase. 

**Utilizar this.**

        using System;
        using System.Collections.Generic;





     namespace tarea2
    {

    class Persona;
    {
        private string nombre;

        
       public Persona(string nombre)
       {
           this.nombre=nombre;
       }

     
      }
    }




**utilizar parametro this**
  
     class Persona 
     {
     private string nombre;

    public Persona(){
   
        this("Kevin"); 
        } 
      
     public Empleado(string Persona){
 
     this.persona=persona
        } 
 

  

  **2.4 Métodos: declaración, mensajes, paso de parámetros, retorno de valores**
   
   Los parámetros declarados para un método sin in, ref o out se pasan a un metodo que es llamada por valor, con esto puedes cambiar el valor de los parametros una ves estando dentro de los metodos, esto solo es temporal ya que cuando termina la llamada del metodo se borran los valores

   estas son las palabras clave para que se comporten diferente los metodos:
   params especifica que este parámetro puede tomar un número variable de argumentos.
*in* especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.
*ref* especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.
*out* especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.



Mediante el uso de la palabra clave params, puede especificar un parámetro de método que toma un número variable de argumentos

se pueden separar por comas en una lista los argumentos pero que sean del tipo especificado en la declaracion del parametro o puede tambien no enviarse nada y es valido, es este caso la longitud de la lista sera cero.(esto varia depende cuantos envies)

despues de la palabra params, ya no se pueden enviar mas parametros.

*out*
Puede usar la palabra clave out en dos contextos:
Como un modificador de parámetro, que le permite pasar un argumento a un método mediante una referencia en lugar de mediante un valor.
En declaraciones de parámetro de tipo genérico para interfaces y delegados, que especifica que un parámetro de tipo es covariante.

*ref*
Esto indica que el parametro ha pasado como referencia 
Puede ser para una llamada al metodo
Puede ser para devolver un valor al autor de la llamada del metodo
Para decir que al devolver un valor al autor este sera alojado de manera local y se podra hacer cambios con el 
En una declaración struct para declarar ref struct o ref readonly struct

Cuando se usa en una lista de parámetros del método, la palabra clave ref indica que un argumento se ha pasado mediante referencia, no por valor.
para usar estos parametros forsozamente se debe utilizar la palara *ref* y para poder pasarse debe estar inicializado en donde se pasara
esto cambia cuando tiene el *out* ya que no se necesita estar inicializado 
en cambio el metodo puede sobrecargarse con este valor mientras haya otro con un valor tambien.



La incorporación del modificador ref a una declaración struct se debe a que las instancias de estos tipos no se pueden crear nunca en el montón como un miembro de otra clase. La principal motivación para esta característica era Span<T> y las estructuras parecidas.
El objetivo de mantener un tipo ref struct como una variable asignada a la pila es para no romper algunas reglas que hay al compilar

No puede encerrar un valor de ref struct. No puede asignar un tipo ref struct a una variable de tipo object, dynamic o cualquier tipo de interfaz.
Los tipos ref struct no pueden implementar interfaces.
No puede declarar un ref struct como miembro de una clase o una estructura normal.
No puede declarar variables locales que sean tipos ref struct en métodos asincrónicos. Puede declararlas en los métodos sincrónicos que devuelven tipos similares a Task, Task<TResult> o Task.
No puede declarar las variables locales de ref struct en iteradores.
No puede capturar variables ref struct en expresiones lambda o funciones locales.


**2.5 Constructores y destructores: declaración, uso y aplicaciones.**

Los constructores son los metodos de las clases que se utilizan al crear un objeto, estos tienen el mismo nombre que la clase y por lo general inicializan el objeto.
un constructor al que  no le envias parametros de dice que es un constructor predeterminado.
estos se invocan cada que se crea un objeto mediante new y no lo das ningun valor.
amenos que la clase sea estatica , las clases que no tengan constructor se les otorgara uno publico con el fin de habilitar las instancias de clase
los constructores para los tipo struct no debes hacerles ninguno porque no se puede ponerle uno expicito sino que el compilador te lo da automaticamente
pero este tipo de constructor solo se puede invocar si las instancias estan hechas con new 
Cualquier constructor puede utilizar la palabra clave base para llamar al constructor de una clase base.
En una clase derivada, si no se llama explícitamente al constructor de la clase base mediante la palabra clave base, se llamará implícitamente al constructor predeterminado
Si una clase base no proporciona un constructor predeterminado, la clase derivada debe realizar una llamada explícita a un constructor base mediante base.
Un constructor puede invocar a otro constructor en el mismo objeto mediante la palabra clave this. Al igual que base, this se puede utilizar con o sin parámetros y cualquier parámetro en el constructor está disponible como parámetro para this o como parte de una expresión.
ademas se utiliza para evitar ambiguedad entre la clase y el constructor.

Los constructores se pueden marcar como public, private, protected, internal o protectedinternal
esto solamente indica de que manera se puede construir la clase, tambien se pueden declarar como estaticos 

