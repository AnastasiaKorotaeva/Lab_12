# Lab_12_1


#include "stdafx.h"
#include <iostream>
#include <ctime>
using namespace std;

const int SIZE = 50;
int getRandom(int min, int max)
{
	static const double fraction = 1.0 / (static_cast<double>(RAND_MAX) + 1.0);
	return static_cast<int>(rand() * fraction * (max - min + 1) + min);
}
void cort(int arr[], const int SIZE)
{
	bool on = false;
	cout << endl << "двузначные числа в массиве : ";
	for (int i = 0; i < SIZE; i++)
	{
		if (arr[i] > 9 && arr[i] < 100)
		{
			cout << arr[i] << " ";
			on = true;
		}
		else if ( i == (SIZE - 1) && on == false)
		{
			cout << " нет двузначных чисел " << endl;
		}
	}

}
int main()
{
	setlocale(LC_ALL, "ru");
	srand(static_cast<unsigned int>(time(0)));
	int mass[SIZE];
	for (int i = 0; i < SIZE; i++)
	{
		mass[i] = getRandom(1 , 1000);
	}
	cout << "изначальный массив диапазон(1-1000)";
	for (int i = 0; i < SIZE; i++)
	{
		if (i % 10 == 0)
		{
			cout << endl << mass[i] << " ";
		}
		else
		{
			cout << mass[i] << " ";
		}
	}
	cort(mass, SIZE);
	cout << endl;
	system("pause");
	return 0;
}
  
  
 Lab_12_2
 
#include "stdafx.h"
#include <iostream>
#include <ctime>
using namespace std;

const int SIZE=20;
int getRandom(int min, int max)
{
	static const double fraction = 1.0 / (static_cast<double>(RAND_MAX) + 1.0);//функция , в которую подается промежуток
	return static_cast<int>(rand() * fraction * (max - min + 1) + min);//возвращение ранд числа в промежутке
}
void sort(int arr[],const int SIZE)//функция для вычисления простых чисел, сортировка 
{
	for (int i = 0; i < SIZE; i++)
	{
		arr[i] = getRandom(1, 10);////присваивание элементу массива ранд числа
		cout << i + 1 << " - " << arr[i] << endl;
	}
}
void zam(int arr[], const int SIZE , int a)//функция замены
{
	for (int i = 0; i < SIZE; i++)

	{
		if (arr[i] % 2 != 0)//проверка нечетности
		{
			arr[i] = a;
		}
		cout<< i+1 << "-" << arr[i] << endl;
	}
}
int main()
{
	int g;
	setlocale(0,"rus");
	srand(static_cast<unsigned int>(time(0)));//с помощью этой функции генерируемые числа всегда будут разные
	int mass[SIZE];
	for(int i = 0; i < SIZE; i++)
	{
		mass[i] = getRandom(10,1000);//присваивание элементу массива ранд числа
	}
	cout << "введите число, на которое будут заменены нечетные числа " << endl;
	cin >> g;
	sort(mass,SIZE);//сортировка по функции 
	zam(mass,SIZE,g);//замена по функции
	system("pause");
	return 0;
}
