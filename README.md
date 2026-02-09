# criando-bandeira-validador-com-copilot

using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Digite o número do cartão:");
        string numero = Console.ReadLine();

        string bandeira = IdentificarBandeira(numero);
        Console.WriteLine($"Bandeira identificada: {bandeira}");
    }

    static string IdentificarBandeira(string numero)
    {
        if (numero.StartsWith("4"))
            return "Visa";
        else if (numero.StartsWith("34") || numero.StartsWith("37"))
            return "American Express";
        else if ((numero.StartsWith("51") || numero.StartsWith("52") ||
                  numero.StartsWith("53") || numero.StartsWith("54") ||
                  numero.StartsWith("55")) ||
                 (int.Parse(numero.Substring(0, 4)) >= 2221 &&
                  int.Parse(numero.Substring(0, 4)) <= 2720))
            return "MasterCard";
        else
            return "Desconhecida";
    }
}
