using System;

public class Calculator
{
    public static void Main(string[] args)
    {
        string operacaoMatematica;
        float num1 = 0f;
        float num2 = 0f;
        string opcao;

        while (true)
        {
            Console.WriteLine("Informe a operação matemática: \n" +
                              " +, -, / ou * ");
            operacaoMatematica = Console.ReadLine();

           
            Console.WriteLine("Informe o primeiro valor:");
            while (!float.TryParse(Console.ReadLine(), out num1))
            {
                Console.WriteLine("Entrada inválida. Por favor, digite um número para o primeiro valor:");
            }

            Console.WriteLine("Informe o segundo valor:");
            
            while (!float.TryParse(Console.ReadLine(), out num2))
            {
                Console.WriteLine("Entrada inválida. Por favor, digite um número para o segundo valor:");
            }

            switch (operacaoMatematica)
            {
                case "+":
                    Console.WriteLine($"Soma: {(num1 + num2):F2}");
                    break;

                case "-":
                    Console.WriteLine($"Subtração: {(num1 - num2):F2}");
                    break;

                case "/":
                    
                    if (num2 != 0)
                    {
                        Console.WriteLine($"Divisão: {(num1 / num2):F2}");
                    }
                    else
                    {
                        Console.WriteLine("Não é possível dividir por zero.");
                    }
                    break;

                case "*":
                    Console.WriteLine($"Multiplicação: {(num1 * num2):F2}");
                    break;

                default:
                    Console.WriteLine("Informe uma opção válida (+, -, /, ou *).");
                    break;
            }

            Console.WriteLine("Deseja continuar (s/n)?");
            opcao = Console.ReadLine().ToLower(); 

            if (opcao != "s")
            {
                break;
            }
        }
        Console.WriteLine("Obrigado por usar a calculadora!");
    }
}
