using System;

class Program
{
    static void Main()
    {
        // Ввод исходного массива строк
        Console.WriteLine("Введите элементы массива через пробел:");
        string input = Console.ReadLine();
        string[] array = input.Split(' ');

        // Формирование нового массива из строк, длина которых <= 3 символов
        string[] newArray = FilterShortStrings(array);

        // Вывод нового массива
        Console.WriteLine("Новый массив:");
        foreach (string str in newArray)
        {
            Console.Write($"{str} ");
        }
    }

    static string[] FilterShortStrings(string[] array)
    {
        // Подсчет количества строк, длина которых <= 3 символов
        int count = 0;
        foreach (string str in array)
        {
            if (str.Length <= 3)
            {
                count++;
            }
        }

        // Создание нового массива нужного размера
        string[] newArray = new string[count];

        // Заполнение нового массива подходящими строками
        int index = 0;
        foreach (string str in array)
        {
            if (str.Length <= 3)
            {
                newArray[index] = str;
                index++;
            }
        }

        return newArray;
    }
}
