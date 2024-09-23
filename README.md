// Homework week 1 task 1 
#define _USE_MATH_DEFINES
#include <iostream>
#include <math.h>
#include <stdio.h>
#include <cmath>
#include <iomanip>
#include <windows.h>

using namespace std;
//int main() {
//	double x, w, f, a, k, T;
//	SetConsoleCP(1251);
//	SetConsoleOutputCP(1251);
//	setlocale(LC_ALL, "ru");
//	cout << "введите значение амплитуды" << endl;
//	cin >> a;
//	cout << "во сколько раз координата меньше амплитуды?" << endl;
//	cin >> k;
//	cout << "введите значение частоты" << endl;
//	cin >> w;
//	f = asin(1 / k);
//	T = (M_PI / 2 - f) / w;
//	x = a * sin(w * T + f);
//	cout << "жпхг" << setprecision(2);
//	cout << "x=" << x << endl;
//	return 0;
//
//}
// Homework week 1 task 2
//int main(){
//	SetConsoleCP(1251);
//	SetConsoleOutputCP(1251);
//	setlocale(LC_ALL, "ru");
//	double H,V,a,x,T,y,g;
//	g = 9.8;
//	cout << "введите значение высоты обрыва" << endl;
//	cin >> H;
//	cout << "введите значение скорости камня" << endl;
//	cin >> V;
//	cout << "введите значение угла к горизонту" << endl;
//	cin >> a;
//	T = (V * sin(a) / g) * (1 + sqrt((1 + 2 * g * H) / pow(V, 2) * pow(sin(a), 2)));
//	x = V * T * cos(a);
//	y = H + V * T * sin(a) - 1 / 2 * g * T * T;
//	cout << "абоба" << setprecision(2) << endl;
//	cout << "x=" << x << endl;
//	cout <<	"y=" << y << endl;
//	return 0;
//}
// Homework week 1 task 3
//int main() {
//	SetConsoleCP(1251);
//	SetConsoleOutputCP(1251);
//	setlocale(LC_ALL, "ru");
//	double x, g, f, per;
//	cout << "введите значение x" << endl;
//	cin >> x;
//	if (-4 < x < -1) {
//		g = abs(x + 6) / abs(x + 3) - 3;
//	}
//	else if (-1 < x < 5) {
//		g = sqrt(5 - x) - 2;
//	}
//	else {
//		g = log(x + 10) - 2;
//	}
//	per = g;
//	if (per < -2) {
//		f = abs(per / (1 - per));
//	}
//	else if (-2 <= per <= 1) {
//		f = pow(per + 2, 2);
//	}
//	else {
//		cout << ("вычислить невозможно — значения вне домена") << endl;
//	}
//	cout << f << endl;
//	return 0;
//}
//Homework week 1 task 4
int main() {
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);
	int x, y, z; // x - скидка; y - взнос; z - плата;
	char kat,client;
	string clientt, pt; // client - клиент; pt - тип оплаты
	double fprice, stavka, konprice;
	cout << "категория товара(A,B,C)=" << endl; 
	cin >> kat;
	cout << "категория клиента(отличный,хороший,средний,плохой)=" << endl;
	cin >> client;
	cout << "начальная стоимость товара" << endl;
	cin >> fprice;
	switch (kat) {
	case 'A':
		if (clientt == "отличный")
		{
			x = 40;
			pt = "нал, чек, кредит";
		}
		if (clientt == "хорошая")
		{
			x = 30;
			pt = "нал, чек, кредит";
		}
		if (clientt == "средний")
		{
			x = 20;
			pt = "нал, чек";
		}
		if (clientt == "плохой")
		{
			x = 0;
			pt = "нал";
		}
		break;
	case 'B':
		if (clientt == "отличный")
		{
			x = 30;
			pt = "нал, чек, кредит";
		}
		if (clientt == "хорошая")
		{
			x = 20;
			pt = "нал, чек, кредит";
		}
		if (clientt == "средний")
		{
			x = 10;
			pt = "нал, чек";
		}
		if (clientt == "плохой")
		{
			x = -5;
			pt = "нал";
		}
		break;
	case 'C':
		if (clientt == "отличный")
		{
			x = 20;
			pt = "нал, чек, кредит";
		}
		if (clientt == "хорошая")
		{
			x = 10;
			pt = "нал, чек, кредит";
		}
		if (clientt == "средний")
		{
			x = 0;
			pt = "нал, чек";
		}
		if (clientt == "плохой")
		{
			x = -10;
			pt = "нал";
		}
		break;
	}
	cout << "способ оплаты" << pt << endl;
	cout << "тип оплаты(нал, чек, кредит)=" << endl;
	cin >> clientt;
	switch (clientt) {
	case 'A':
		konprice = fprice - 0.01 * (x * fprice);
	case 'B':
		cout << "количество взносов" << endl;
		cin >> y;
		cout << "процентная ставка(3%-15%)" << endl;
		cin >> z;
		konprice = fprice * (1 + z * y / 100);
		konprice = konprice - 0.01 * (x * konprice);
	case 'C':
		cout << "количество платежей(1-6)" << endl;
		cin >> y;
		cout << "тип кредита(платиновый-1, бизнес-2)" << endl;
		cin >> z;
		if (z == 1) {
			stavka = 5;
		}
		else {
			stavka = 2;
		}
		konprice = pow(fprice * (1 + stavka / 100), y);
		konprice = konprice - 0.01 * (x * konprice);
	}
	cout << "fixed" << setprecision(2);
	cout << "конечная цена=" << konprice << endl;
	return 0;
}
