using System;
using System.Collections.Generic;
using System.Linq;
using System.Net.NetworkInformation;
using System.Text;
using System.Threading.Tasks;

namespace LevelUpMath
{
    internal class Program
    {

        enum e_Operateur
        {
            ADDITION = 1,
            SOUSTRACTION = 2,
            MULTIPLICATION = 3
        }

        static bool PoserQuestion(int min, int max)
        {
            Random rand = new Random();
            int reponseInt = 0;
            while (true)
            {
                int a = rand.Next(min, max + 1);
                int b = rand.Next(min, max + 1);
                e_Operateur o = (e_Operateur)rand.Next(1, 4);
                int resultatAttendu;

                switch (o)
                {
                    case e_Operateur.ADDITION:
                        Console.Write($" {a} + {b} = ");
                        resultatAttendu = a + b;
                        break;
                    case e_Operateur.SOUSTRACTION:
                        Console.Write($" {a} - {b} = ");
                        resultatAttendu = a - b;
                        break;
                    case e_Operateur.MULTIPLICATION:
                        Console.Write($" {a} x {b} = ");
                        resultatAttendu = a * b;
                        break;
                    default:
                        Console.WriteLine("ERREUR : opérateur inconnu");
                        return false;
                }

                string reponse = Console.ReadLine();
                try
                {
                    reponseInt = int.Parse(reponse);
                    if (reponseInt == resultatAttendu)
                    {
                        return true;
                    }
                    return false;
                }
                catch (Exception)
                {
                    Console.WriteLine("Erreur: vous devez entrer un nombre");
                }
            }
        }
        static void Main(string[] args)
        {

            const int NOMBRE_MIN = 1;
            const int NOMBRE_MAX = 10;
            const int NB_QUESTIONS = 5;

            int points = 0;

            for (int i = 0; i < NB_QUESTIONS; i++)
            {
                Console.WriteLine($"Question numéro {i + 1} / {NB_QUESTIONS}");
                bool bonneReponse = PoserQuestion(NOMBRE_MIN, NOMBRE_MAX);
                if (bonneReponse)
                {
                    Console.WriteLine("Bonne reponse");
                    points++;
                }
                else
                {
                    Console.WriteLine("Mauvaise reponse");
                }
            }
            Console.WriteLine($"Vous avez {points} bonne réponse, votre score est de {points} / {NB_QUESTIONS}.");

            int moyenne = NB_QUESTIONS / 2;
            //float moyenneFloat = NB_QUESTIONS / 2f;
            //Console.WriteLine($"moyenne float = {moyenneFloat} | moyenne int = {moyenne}");

            if (points == NB_QUESTIONS)
            {
                Console.WriteLine("Excellent");
            }
            else if (points == 0)
            {
                Console.WriteLine("Revise tes maths");
            }
            else if (points > moyenne)
            {
                Console.WriteLine("Pas mal");
            }
            else if (points < moyenne)
            {
                Console.WriteLine("Peux mieux faire");
            }
            else
            {
                Console.WriteLine("Erreur");
            }
        }
    }
}
