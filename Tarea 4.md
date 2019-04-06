**1.1.¿Qué valores imprimen las lineas (1) y (2)?**

Imprimen 10 y 10.

**1.2.Redefine el método Display en el espacio indicado, una vez redefinido el método, ¿qué valores imprimen las lineas (1) y (2)?.**

10 y 15 en ese orden.

**1.3.¿Que palabra debes agregar en la linea (public _____ string Display()) al definir A.Display()?**
virtual para después poder redefinir con override.

**Así me quedó el código al final**

     using System;

      namespace tarea4
     {


        class A

       {

          public int a;

          public A()

          {

              a = 10;

          }

          public virtual  string Display()

          {

            return a.ToString();

          }

      }

      class B : A

      {

          public int b;

          public B() : base()

          {

            b = 15;

          }



        public override string Display()

         {

            return b.ToString();

         }


     }

     class Program

     {

        static void Main(string[] args)

        {

            A objA = new A();

            B objB = new B();

            Console.WriteLine(objA.Display()); ////  (1 )

            Console.WriteLine(objB.Display()); ////  ( 2)

            Console.ReadKey();
            

        }

      }

     }

**2.1. Completa el programa.**
**Aqui está el programa terminado abstracto**
             
             
             using System;
      using System.Collections.Generic;

       abstract class Musico 

    {

        public string nombre;
   
        public Musico(string n)

        {

            nombre = n;

        }

           public virtual void Afina()
        {

            Console.WriteLine("  Está afinado");
        }
       

    }

    class Bajista : Musico

    {

        public string instrumento;

        public Bajista(string n, string i) : base(n)
        {

         instrumento=i;
        }


        public override void Afina()

        {

        Console.WriteLine("El bajista  está afinado");
        }

           public override string ToString ()
           {
            return string.Format("Nombre : {0},{1} ", nombre,instrumento);
           }
    }

       class Guitarrista : Musico

      {

        public string instrumento;
     public Guitarrista(string n, string i): base (n)
        {
            instrumento = i;
        }

        public virtual new void Afina()

        {

            Console.WriteLine("El guitarrista  está afinado");

   

        }

        public override string ToString()
        {
            return string.Format("Nombre : {0},{1} ", nombre, instrumento);
        }


    }



    class Program

    {

         static void Main()

    {

       

        Bajista b = new Bajista("Flea","bajista");

        Guitarrista g = new Guitarrista("Santana","Guitarrista");

            List<Musico> musicos = new List<Musico>();

            musicos.Add(b);
            musicos.Add(g);
            


           



            foreach (Musico x in musicos)
            {
                
               

               Console.WriteLine(x);
            }


            // (m as IAfina).Afina()

            Console.ReadKey();



    }

    }
             
   


**2.2.Hay un error en uno de los puntos (A)(B)(C)(D). ¿Cuál es y por qué?**
En el (B), no lleva punto y coma.
en el (C), se debe redefinir el string
el (D), no le encuentro errores



**2.3.¿Qué método se debe implementar obligatoriamente en ambas clases y por qué?**

Afina(), porque viene heredado de la clase abstracta y en clase abstracta todo se debe implementar.

**2.4.¿Por qué no se ponen las llaves en (B)?, ¿Cuando si se pondrían?**
porque no lo estaba redefiniendo,un ejemplo
              
              public  void Afina()
        {

            Console.WriteLine("  Está afinado");
        }

**2.5.¿Qué pasa si el método Afina() lo hacemos virtual en lugar de abstract?**
Alguno podria no implementarlo si esta virtual, si esta abstracto debe ser en todos forzosamente.



**3.Implementa el programa utilizando interfaces en lugar de herencia.**
  using System;
           using System.Collections.Generic;



          



    
    interface IAfina
    {
    
    void Afina();
    }

    class Musico : IAfina

    {

        public string nombre;
   
        public Musico(string n)

        {

            nombre = n;

        }

    public void Afina()
        {

            Console.WriteLine("  Está afinado");
        }
        public  override string ToString ()

        {

         return string.Format("Nombre : {0}", nombre);

        }

    }

    class Bajista : Musico,IAfina

    {

        public string instrumento;

        public Bajista(string n, string i) : base(n)
        {

         instrumento=i;
        }


        public virtual new void Afina()

        {

        Console.WriteLine("El bajista  está afinado");
        }

           public override string ToString ()
           {
            return string.Format("Nombre : {0},{1} ", nombre,instrumento);
           }
    }

       class Guitarrista : Musico,IAfina

       {

        public string instrumento;
     public Guitarrista(string n, string i): base (n)
        {
            instrumento = i;
        }

        public virtual new void Afina()

        {

            Console.WriteLine("El guitarrista  está afinado");



        }

        public override string ToString()
        {
            return string.Format("Nombre : {0},{1} ", nombre, instrumento);
        }


    }



    class Program

    {

         static void Main()

    {

        Musico m = new Musico("Django"); 

        Bajista b = new Bajista("Flea","bajista");

        Guitarrista g = new Guitarrista("Santana","Guitarrista");

            List<Musico> musicos = new List<Musico>();

            musicos.Add(b);
            musicos.Add(g);
            musicos.Add(m);


           



            foreach (Musico x in musicos)
            {
                (b as IAfina).Afina();
                (g as IAfina).Afina();
                (m as Musico).Afina();

               Console.WriteLine(x);
            }


            // (m as IAfina).Afina()

            Console.ReadKey();



    }

    }
