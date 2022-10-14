

using System;

using System.Net.NetworkInformation;


namespace Programa
{

    class Program
    
    {
    
        struct Menu
        
        {

            public string nombre;
            public string usuario;
            public string contra;
            public double saldo;
            public int abonar;
            public string retirar;




        }

        struct Platillo
        {
            public string platillo;
            public string cali;

        }

        struct Pelicula
        {
            public string pelicula;
            public string calif;

        }
        static void Main(string[] args)
        {
            Menu p = new Menu();
            Platillo a = new Platillo();
            Pelicula g = new Pelicula();
            bool correrPrograma = true;
            while (correrPrograma == true)
            {
                ImprimirMenu();
                int opcion = Convert.ToInt32(Console.ReadLine());
                switch (opcion)
                {
                    case 1:
                        p = Sordo();

                        LimpiarConsola();
                        break;

                    case 2:
                        Ver(ref p);
                        LimpiarConsola();
                        break;



                    case 3:
                        correrPrograma = false;
                        break;

                }
            }
        }
        static void LimpiarConsola()
        {
            Console.Write("Presione Enter para continuar...");
            Console.ReadLine();
            Console.Clear();
        }
        static void ImprimirMenu()
        {
            Console.WriteLine("Menu");
            Console.WriteLine("-----------------------");
            Console.WriteLine("1 Alta de Usuario");
            Console.WriteLine("2 Acceder ");
            Console.WriteLine("3 Salir");
            Console.WriteLine("----------------------");

            Console.Write("Elegir opcion: ");

        }
        static Menu Sordo()
        {
            Menu autoTemporal = new Menu();


            Console.Write("Ingrese su nombre : ");
            autoTemporal.nombre = Console.ReadLine();
            Console.Write("Ingrese su nombre de usuario :");
            autoTemporal.usuario = Console.ReadLine();
            Console.Write("Ingrese un saldo:  $"); 
            autoTemporal.saldo = Convert.ToInt32(Console.ReadLine());
            Console.Write("Ingrese una contraseña: ");
            autoTemporal.contra = Console.ReadLine();
            return autoTemporal;
        }
        static void Ver(ref Menu p)
        {



            Console.WriteLine("Ingrese su Usuario");
            string confirmación = Console.ReadLine();

            if (confirmación == p.usuario)
            {


                Console.WriteLine("Ingrese su contraseña");
                string confirmación2 = Console.ReadLine();
                if (confirmación2 == p.contra)
                {
                    Platillo a = new Platillo();
                    Pelicula g = new Pelicula();

                    bool correrPrograma = true;
                    while (correrPrograma == true)
                    {

                        ImprimirMenu();
                        int opcion = Convert.ToInt32(Console.ReadLine());
                        switch (opcion)
                        {
                            case 1:
                                Informacion(ref p);
                                LimpiarConsola();
                                break;

                            case 2:
                                Saldo(ref p);
                                LimpiarConsola();
                                break;

                            case 3:
                                p = Abonar(ref p);
                                LimpiarConsola();
                                break;

                            case 4:
                                retirar(ref p);
                                LimpiarConsola();
                                break;




                            case 5:
                                correrPrograma = false;
                                break;




                        }
                        static void ImprimirMenu()
                        {
                            Console.WriteLine("ACCESO DE SISTEMA");
                            Console.WriteLine("-----------------------");
                            Console.WriteLine("1 Ver  informacion de la cuenta");
                            Console.WriteLine("2 Ver saldo  ");
                            Console.WriteLine("3 abonar cuenta");
                            Console.WriteLine("4 retirar de la  cuenta ");
                            Console.WriteLine("5 Salir");
                            Console.WriteLine("----------------------");

                            Console.Write("Elegir opcion: ");

                        }

                        static void Informacion(ref Menu p)
                        {

                            Console.WriteLine($"El nombre es:{p.nombre}");
                            Console.WriteLine($"El usuario es :{p.usuario}");
                            Console.WriteLine($"La contraseña es : {p.contra}");



                        }

                        static void Saldo(ref Menu p)
                        {
                            Console.WriteLine($"Tu saldo es :$ {p.saldo}");

                        }

                        static Menu Abonar(ref Menu p)
                        {
                            Console.Write("Ingrese lo que quiera abonar  :$ ");
                            p.saldo += Convert.ToInt32(Console.ReadLine());

                            Console.Write($"Su saldo ahora es de  :${p.saldo} ");


                            return p;



                        }
                        static Menu retirar(ref Menu p)
                        {
                            Console.Write("Ingrese lo que quiere retirar:$ ");
                            double retirar = Convert.ToDouble(Console.ReadLine());
                            p.saldo = p.saldo - retirar;
                            Console.Write($"Su saldo ahora es de  :${p.saldo}");

                            return p;



                        }






                    }

                }


                else
                {
                    Console.WriteLine("Contraseña incorrecta intente de nuevo ");
                }






            }
            else
            {
                Console.WriteLine("Usuario no encontrado intente de nuevo");
            }
        }
    }
}
