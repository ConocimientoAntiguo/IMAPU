# Recursividad

El lenguaje permite que una funcion se pueda emplear a si misma de manera directa o indirectmente, a esto se le denomina recursividad.

	* Ejemplo
		#include<stdio.h>
		
		int potencia(int b, int e);

		int main(){
			int a = 5, i=4;
			printf("%d elevado a la %d = %d ",a,i,potencia(5,4));
		return 0;
		}
	
		int potencia(int b, int e){
			if(e == 0)
				return 1;
			else
				return (b * potencia(b,e - 1));
		}
