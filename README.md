#include<iostream>
#include<stdio.h>
#include<cstdlib>
using namespace std;
 
void menuadmin();
void ainventario();
void menusuario();
void busqueda();
void listado();
void boleta();
void consultarstock();
void mprecio();
void vender(int a);
 
int cantidadproductos=5;
string producto[100][40] ,compuestos[100][100],info[100][100];
int stock[100];
float precio[100];
int cvendidos[50],pvendidos=0,IDproducto[100];
 
int main()
{
	producto[0][40] = "LERGIUM PLUS";
	stock[0] = 50;
	precio[0] = 2.5;
	compuestos[0][100] = "Cetirizina + Seudoefedrina";
	info[0][100] = "Descongestivo nasal antihistamínico";
	producto[1][40] = "PANADOL";
	stock[1] = 50;
	precio[1] = 1.2;
	compuestos[1][100] = "Paracetamol";
	info[1][100] = "Analgésico antipirético";
	producto[2][40] = "AMOXICILINA";
	stock[2] = 45;
	precio[2] = 1.8;
	compuestos[2][100] = "Amoxicilina";
	info[2][100] = "Antibiótico bactericida";
	producto[3][40] = "ESPASMO ANTALGINA";
	stock[3] = 100;
	precio[3] = 1.5;
	compuestos[3][100] = "Dipirona + Hioscina butilbromuro";
	info[3][100] = "Analgésico espasmolítico";
	producto[4][40] = "DOLOSAN FORTE";
	stock[4] = 120;
	precio[4] = 1.8;
	compuestos[4][100] = "Diclofenac + Paracetamol";
	info[4][100] = "Analgésico antiinflamatorio antipirético";
	preguntar:
	system("cls");
	cout<<" =============================================================================="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =                        FARMACIA ''JUSTIN WEAVER''                          ="<<endl;
	cout<<" =                                                                            ="<<endl; 
	cout<<" =         Opci"<<char(162)<<"n 1. Men"<<char(163)<< " usuario.                                            ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =         Opci"<<char(162)<<"n 2. Men"<<char(163)<< " administrador                                       ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =============================================================================="<<endl;
	cout<<" Ingrese una opci"<<char(162)<<"n: ";
	int u;
	cin>>u;
	switch(u)
	{
		case 1: menusuario();
				break;
		case 2:	menuadmin();
				break;
		default:	
				system("cls");
				cout<<"Opci"<<char(162)<<"n Inv"<<char(160)<<"lida";
				goto preguntar;
				break;	
	}
}
void menuadmin()
{
	system("cls");
	cout<<" =============================================================================="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =                        MEN"<<char(233)<< " ADMINISTRADOR                                  ="<<endl;
	cout<<" =                                                                            ="<<endl; 
	cout<<" =                                                                            ="<<endl;
	cout<<" =============================================================================="<<endl;
	cout<<" Por favor ingrese su contrase"<<char(164)<<"a: ";
	string pass;
	cin>>pass;
	if(pass=="2")
	{
		system("cls");
		int opcion;
		cout<<" =============================================================================="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =                        MEN"<<char(233)<< " ADMINISTRADOR                                  ="<<endl;
		cout<<" =                                                                            ="<<endl; 
		cout<<" =         Opci"<<char(162)<<"n 1. Agregar un producto.                                     ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =         Opci"<<char(162)<<"n 2. Venta de productos.                                      ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =         Opci"<<char(162)<<"n 3. Modificar precios.                                       ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =         Opci"<<char(162)<<"n 4. Cerrar sesi"<<char(162)<<"n.                                           ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =============================================================================="<<endl;
		cout<<"\n Ingrese una opci"<<char(162)<<"n: ";
		cin>>opcion;
		switch(opcion)
		{
			case 1: ainventario();
					break;
			case 2: consultarstock();
					break;
			case 3:	mprecio();
					break;
			case 4:	system("cls");
					cout<<"Sesi"<<char(162)<< "n cerrada."<<endl;
					cin.get();
					cin.get();
					main();
					break;
			default:
					system("cls");
					cout<<"Opci"<<char(162)<<"n inv"<<char(160)<<"lida."<<endl;
					system("pause");
					menuadmin();
		}
		menuadmin();
	}
	else 
	{
		system("cls");
		cout<<"Contrase"<<char(164)<<"a incorrecta."<<endl;
		system ("pause");
		menuadmin();
	}
}
void menusuario()
{
	system("cls");
	int opcion;
		cout<<" =============================================================================="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =                        MEN"<<char(233)<< " USUARIO                                        ="<<endl;
		cout<<" =                                                                            ="<<endl; 
		cout<<" =         Opci"<<char(162)<<"n 1. Venta de productos.                                      ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =         Opci"<<char(162)<<"n 2. Cerrar sesi"<<char(162)<<"n.                                           ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =============================================================================="<<endl;
	cout<<"\n Ingrese una opci"<<char(162)<<"n: ";
	cin>>opcion;
	switch(opcion)
	{
		case 1: consultarstock();
				break;
		case 2:	system("cls");
				cout<<"\tSesi"<<char(162)<< "n cerrada."<<endl;
				cin.get();
				cin.get();
				main();
				break;
		default:
				system("cls");
				cout<<"Opci"<<char(162)<<"n inv"<<char(160)<<"lida."<<endl;
				system("pause");
				menusuario();
	}
	menusuario();
}
 
void ainventario()
{
	system("cls");
	int n,m,contador=1,existe=0,pe=0;;
	string aux;
	cout<<"\n"<<char(168)<< "Cu"<<char(160)<<"antos medicamentos desea agregar?: ";
	cin>>n;
	cin.ignore();
	for(int i=cantidadproductos; i<n+cantidadproductos; i++)
	{
		cout<<"\n Ingrese el nombre del producto "<<contador<<": ";
		getline(cin,aux);
		for(int j=0; j<n+cantidadproductos-1;j++)
		{
			if(aux==producto[j][40])
			{
				cout<<"\n\tEl producto ingresado ya tiene "<<stock[j]<<" existencias."<<endl;
				m=j;
				i-=1;
				n-=1;
				existe=1;
			}
		}
		if(existe==0)
		{
			producto[i][40]=aux;
			cout<<"\n\tIngrese los compuestos del producto: ";
			getline(cin,compuestos[i][100]);
			cout<<"\n\tIngrese la informaci"<<char(162)<< "n del producto: ";
			getline(cin,info[i][100]);
			cout<<"\n\tIngrese el precio por unidad: S/. ";
			cin>>precio[i];
			cout<<"\n\tIngrese stock inicial: ";
			cin>>stock[i];
		}
		else
		{
			cout<<"\n\t"<<char(168)<< "Cu"<<char(160)<< "ntas unidades desea agregar? ";
			int agregar;			
			cin>>agregar;
			stock[m]+=agregar;
		}
		cin.ignore();	
		contador+=1;
		existe=0;	
	}
	cantidadproductos=cantidadproductos+n;
	cout<<"\n\tProducto(s) agregados con "<<char(130)<<"xito!."<<endl;
	cin.get();
}
void consultarstock()
{
	system("cls");
	int opcion;
	cout<<" =============================================================================="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =                        VENTA DE PRODUCTOS                                  ="<<endl;
	cout<<" =                                                                            ="<<endl; 
	cout<<" =         Opci"<<char(162)<<"n 1. Buscar un producto por su nombre.                        ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =         Opci"<<char(162)<<"n 2. Lista de productos.                                      ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =         Opci"<<char(162)<<"n 3. Hacer boleta.                                            ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =         Opci"<<char(162)<<"n 4. Cerrar sesi"<<char(162)<<"n.                                           ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =============================================================================="<<endl;
	cout<<"\nIngrese su opci"<<char(162)<<"n: ";
	cin>>opcion;
	switch(opcion)
	{
		int a;
		case 1: busqueda();
				break;
		case 2: listado();
				break;
		case 3:	boleta();
				break;
		case 4:	system("cls");
				cout<<"Sesi"<<char(162)<< "n cerrada."<<endl;
				cin.get();
				cin.get();
				main();
				break;
		default:
				system("cls");
				cout<<"Opci"<<char(162)<<"n inv"<<char(160)<<"lida."<<endl;
				cin.get();
				cin.get();
				consultarstock();
				break;
	}
}
void busqueda()
{
	int i=0;
	bool salir=true;
	string aux;
	system("cls");
	cout<<"\n\tIngrese el nombre del producto: ";
	cin.ignore();
	getline(cin,aux);
	volver:
	system("cls");
		do
		{
			if(aux==producto[i][40])
			{
				cout<<" =============================================================================="<<endl;
				cout<<" =                                                                            ="<<endl;
				cout<<" =                   Producto: "<<producto[i][40]<<endl;
				cout<<" =                                                                            ="<<endl;
				cout<<" =     Compuestos: "<<compuestos[i][100]<<endl;
				cout<<" =                                                                            ="<<endl;
				cout<<" =     Informaci"<<char(162)<<"n: "<<info[i][100]<<endl;
				cout<<" =                                                                            ="<<endl;
				cout<<" =     Existencias: "<<stock[i]<<endl;
				cout<<" =                                                                            ="<<endl;
				cout<<" =     Precio por unidad: S/. "<<precio[i]<<endl;
				cout<<" =                                                                            ="<<endl;
				cout<<" =============================================================================="<<endl;					
				salir=false;
			}
			else
			{
				i++;
				if(i==cantidadproductos)
					salir=false;
			}
		}while(salir==true);
		if(i<cantidadproductos)
		{
			vender(i);
		}
		else
		{
			cout<<"Producto no encontrado."<<endl;
		}
		cin.get();
	consultarstock();				
}
void listado()
{
	int opcion,n,aux,i;
		system("cls");
		cout<<" =============================================================================="<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =                               PRODUCTOS                                    ="<<endl;
		cout<<" =                                                                            ="<<endl;
		for(i=0;i<cantidadproductos;i++)
		{
			cout<<" =\t\t"<<"Opci"<<char(162)<<"n "<<i+1<<".-"<<producto[i][40]<<endl;
			cout<<" =                                                                            ="<<endl;
		}
		cout<<" =                                                                            ="<<endl;
		cout<<" =============================================================================="<<endl;
		cout<<"\n Ingrese su opci"<<char(162)<<"n: ";
		cin>>opcion;
		opcion-=1;
		if(opcion<i && opcion>=0)
		{
			system("cls");
			cout<<" =============================================================================="<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =                   Producto: "<<producto[opcion][40]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =     Compuestos: "<<compuestos[opcion][100]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =     Informaci"<<char(162)<<"n: "<<info[opcion][100]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =     Existencias: "<<stock[opcion]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =     Precio por unidad: S/. "<<precio[opcion]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =============================================================================="<<endl;
			vender(opcion);	
		}
		else
		{
			system("cls");
			cout<<" Opci"<<char(162)<< "n inv"<<char()<< "lida."<<endl;
			cin.get();
			cin.get();
			listado();
		}
			
		consultarstock();
}
void boleta()
{
	system("cls");
	string cliente;
	cout<<"\n\tIngrese el nombre del cliente: ";
	cin.ignore();
	getline(cin,cliente);
	system("cls");
	float total=0;
	cout<<" =============================================================================="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =                            BOLETA DE VENTAS                                ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =    Cliente: "<<cliente<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =----------------------------------------------------------------------------="<<endl;
	for(int i=0; i<pvendidos; i++)
	{
		cout<<" =                                                                            ="<<endl;
		cout<<" =  Producto vendido: "<<producto[IDproducto[i]][40]<<endl;
		cout<<" =  Unidades vendidas: "<<cvendidos[i]<<endl;
		cout<<" =  Precio por unidad: S/. "<<precio[IDproducto[i]]<<endl;
		cout<<" =  Precio total por producto: S/. "<<precio[IDproducto[i]]*cvendidos[i]<<endl;
		cout<<" =                                                                            ="<<endl;
		cout<<" =----------------------------------------------------------------------------="<<endl;
		total+=precio[IDproducto[i]]*cvendidos[i];
	}
	cout<<" =                                                                            ="<<endl;
	cout<<" =                          PRECIO TOTAL: S/."<<total<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =    GRACIAS POR COMPRAR EN FARMACIA ''JUSTIN WEAVER''                       ="<<endl;
	cout<<" =                                                                            ="<<endl;
	cout<<" =============================================================================="<<endl;
	pvendidos=0;
	system("pause");
}
void mprecio()
{
	string nombre;
	int i=0;
	bool salir=true;
	system("cls");
	cout<<"\n\tIngrese el nombre del producto: ";
	cin.ignore();
	getline(cin,nombre);
	do
	{
		if(nombre==producto[i][40])
		{
			cout<<" =============================================================================="<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =  Producto: "<<producto[i][40]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =  Precio actual: S/. "<<precio[i]<<endl;
			cout<<" =                                                                            ="<<endl;
			cout<<" =============================================================================="<<endl;
			cout<<"Ingrese nuevo precio: ";
			cin>>precio[i];
			salir=false;
			cout<<"Precio cambiado satisfactoriamente!"<<endl;
			system("pause");
		}
		else
		{
			i++;
			if(i==cantidadproductos)
				salir=false;
		}
	}while(salir==true);
	if(salir==false)
	{
		cout<<"Producto no encontrado."<<endl;
		cin.get();
	}
}
void vender(int a)
{
	volver:
	cout<<"\n "<<char(168)<< "Cu"<<char(160)<<"ntas unidades desea vender?(presione 0 si desea salir) ";
	cin>>cvendidos[pvendidos];
	if(cvendidos[pvendidos]<0)
	{
		cout<<"\nLa cantidad tiene que ser positiva"<<endl;
		goto volver;
	}
	else
	{
		if(cvendidos[pvendidos]==0);		
		else if(cvendidos[pvendidos]<=stock[a])
		{
			stock[a]=stock[a]-cvendidos[pvendidos];
			IDproducto[pvendidos]=a;
			cout<<" Se vendieron "<<cvendidos[pvendidos]<<" unidades."<<endl;
			pvendidos+=1;
			cin.get();
			cin.get();
		}
		else
		{
			system("cls");
			cout<<"	No hay suficientes unidades."<<endl;
			cin.get();
			cin.get();
		}
	}
}
