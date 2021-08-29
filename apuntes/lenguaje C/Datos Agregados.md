## Tipos de Datos Agregados

Estructura: Es un tipo de dato que tiene variables agrupadas bajo un mismo nombre.

	* Ejemplo
		#include<stdio.h>
		
		typedef struct caja{
		  int codigo;
		  char tipo;
		  float costo;
		}caja;
	
		int main(){
	  	  caja cereal = {123,'N',65.5};
		  
		  printf("codigo %d",cereal.codigo);
		  return 0;
		}

Uniones: Es similar a una estructura. La diferencia está en que todos los miembros de la unión comparten el mismo espacio en memoria.


	* Ejemplo
	 	#include<stdio.h>
		
		union conjunto{
			int a;
			int b;
			int c;
		};
		
		int main(){
  	
			union conjunto numeros;
	
			printf("Numero 1:");
			scanf("%d",&numeros.a);
			printf("Numero 2:");
			scanf("%d",&numeros.b);
			printf("Numero 3:");
			scanf("%d",&numeros.c);
	 

			printf("El valor del numero 1: %d\n",numeros.a);
			printf("El valor del numero 2: %d\n",numeros.b); 
			printf("El valor del numero 3: %d\n",numeros.c);
			
		return 0;
		}
     	

Enumeraciones: Es un tipo de dato que esta conformado por constantes numericas enteras con identificadores en tipo de lista, si no se declara un valor inicial las enumeraciones comienzan en el 0.
	
	* Ejemplo
		#include<stdio.h>
		
		enum numero{
		ENERO=1,FEBRERO,MARZO,ABRIL,MAYO,JUNIO,JULIO,AGOSTO,SEPTIEBRE,OCTUBRE,NOVIEMBRE,DICIEMBRE
		};

		int main(){
	
			enum numero mes;
	
			for(mes=ENERO; mes<=DICIEMBRE;mes++){
				printf("El numero del mes es: %d\n",mes);
			}
		return 0;
		}
