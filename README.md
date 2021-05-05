**UNIVERSIDADE LUSÓFONA DE HUMANIDADES E TECNOLOGIAS**

*Linguagens de Programação I - 2019/2020*

# Ficha de Exercícios - 6: Ponteiros

## Recomendações
Na resolução destes exercícios deve ser utilizada a Linguagem de Programação C. Para além da correta implementação dos requisitos, tenha em conta os seguintes aspetos:

- O código apresentado deve ser bem indentado. 
- O código deve compilar sem erros ou *warnings* utilizando o *gcc* com as seguintes flags:
- `gcc -Wall -Wextra -Wpedantic -ansi -g exercicio1.c -o exercicio1`
- Tenha em atenção os nomes dados das variáveis, para que sejam indicadores daquilo que as mesmas vão conter.
- Evite o uso de constantes mágicas. 
- Evite duplicação de código. 
- Considere a implementação de funções para melhorar a legibilidade, evitar a duplicação e criar soluções mais genéricas.

## Níveis de exercícios
Nesta ficha existem dois níveis de exercícios:
* **[A]**: exercícios relacionados com Apontadores (aula teórica de Apontadores)
* **[A2]**: exercícios relacionados com Aritmética de Apontadores (aula teórica de Aritmética de Apontadores)
 

## Exercicios de Apontadores [A]


1. Considere a seguinte sequência de instruções:
    ```C
	int var1 ;
	int var2 = 15;
	int * ptr = & var1 ;
	int * ptr2 = ptr;
	*ptr = var2 ;
    ```
   Complete a tabela em baixo preenchendo o conteúdo das variáveis var1, ptr e ptr2 no fim da execuçãao da sequência de instruções. Preencha também o endereço correspondente à variável var2 assumindo que este é o próximo endereço livre possível.
   

	| Endereço | Conteúdo | Identificador |
	|:--------:|:--------:|:-------------:|
	|    ...   |          |               |
	|  0xFF8B4 |          |      var1     |
	|          |    15    |      var2     |
	|    ...   |          |               |
	|  0xFF900 |          |      ptr      |
	|  0xFF908 |          |      ptr2     |
	|    ...   |          |               |


2. Implemente um programa que contenha duas variáveis x e y do tipo int e float, ambas inicializadas com o valor 5. Declare também dois apontadores px e py, que apontam para x e y respetivamente.

	Em seguida mostre o valor das variáveis e o seu endereço armazenado no respetivo apontador. Depois mostre o valor das mesmas variáveis incrementado em uma unidade.
	
	*Notas:*
	Transforme os endereços num long int para melhor compreensão dos resultados.


3. Qual o valor das variáveis x, y e z no fim da execução do programa?

    ```C
	#include <stdio.h>
	void func(int n, int * a, int * b)
	{
	   n = *a;
	   *a = *b;
	   *b = n++;
	}
	int main(void)
	{
	   int x = 10, y = 15, z = 5;
	   func(z, &x, &y);
	   printf("x = %d, y = %d, z = %d\n", x, y, z);
	   return 0;
	}
    ```
 
    

4. Considere o seguinte código:
    ```C
    int main (int argc, char * argv[]) {
      int numero = 10;  
      int * pNum = NULL;    
      return 0;  
    }    

    ```
    Altere o código para:
    
    a) O ponteiro pNum ficar a apontar para a variável número;
    
    b) Apresente no ecrã o valor da variável número, sem a usar diretamente (ou seja, usando o ponteiro pNum;
    
    c) Altere (por ex. para 15) o valor da variável número sem a usar diretamente (ou seja, usando o ponteiro pNum);
    
    d) Apresente novamente no ecrã o valor da variável número, usando o ponteiro pNum;


6. Implemente uma função que receba uma string  (char *)  e devolva o endereço da  primeira vogal que existe nessa string. Caso não exista nenhuma vogal a função deve devolver  NULL.

    Sugere-se que a função tenha o seguinte protocolo:    
    ```C
    char* primeiraVogal (char *str) {  ...  }
    ```
    

7. Considere as funções main () e calcular_dados() que se seguem:
    ```C
    void calcular_dados (...) {  // TODO  }   

    int main () 
    { 
      int x = 10, y = 15;
      int soma;  
      float media;    
      calcular_dados (...); // TODO    
      printf("Soma = %d\n", soma);  
      printf("Media = %f\n", media);    
      return 0;  
    }
    ```
    
    O objetivo do exercício é implementar a função calcular_dados(...) de maneira a que possa ser usada para calcular a soma e a média de dois números.   
 	Restrições:    
    - A única linha da função main () que pode alterar é a linha da chamada à função  calcular_dados () .    
    -	O cálculo da soma e da média dos dois valores tem obrigatóriamente de ser feito  usando a função calcular_dados  ()
    - Não pode alterar o tipo de retorno da função calcular_dados  ()
    - Não pode usar variáveis globais para resolver este exercício. 



8. Implemente uma função que seja capaz de determinar qual o maior e menor valores de um vetor de inteiros. A função deve respeitar a seguinte assinatura:
    ```C
    void calcMinimoEMaximo (int numeros[], int tamanho, int *min, int *max ) {  }
    ```
    Os valores do menor e maior números devem ser guardados nas posições de memória para as  quais apontem os parâmetros min e max  (ponteiros)  que a função recebe.


9. Considere o array argv[], que faz parte da assinatura standard da função main,  e que permite receber argumentos de linha de comandos, durante a execução do programa.
    ```C
    int main (int argc, char* argv[]) 
    { 
 		  /* … */  
      return 0;  
    }
    ```
    
    O parâmetro argc tem o número de argumentos e o parâmetro argv[] tem os valores dos argumentos.
    Implemente um programa que seja capaz de obter valores indeterminados como argumentos de linha de comandos. O programa deve listar os vários argumentos, precedidos de um prefixo numérico, que deve começar em 1. Caso não seja fornecido nenhum argumento, o programa deve apresentar uma mensagem indicativa.

    Seguem-se três exemplos de sessões do programa:
    ```bash
    > nome_programa.exe
    Não foram introduzidos argumentos.
    > nome_programa.exe ola  
    Os argumentos são:  1 ola    
    > nome_programa.exe ola ole  
    Os argumentos são:  1 ola  2 ole
    ```
    *Notas:*
    - Tenha em conta que argv[0] irá conter o nome do programa. Esse argumento não deverá aparecer no seu output.


10.  Implemente um programa que some todos os números passados na linha de comando.

	Exemplo:
	```bash
	> Soma
	0
	> Soma 10 20 30
	60
	> Soma 10 20 30 -5
	55
	```
	
11. Implemente um programa que mostre uma string no ecrã pela ordem em que está escrita e pela ordem contrária. Use somente duas variáveis (char str[100] e char *ptr)


12. Implemente a função myStrcpy que copia a string orig para a string dest.
	```C
	char *myStrcpy(char *dest, char *orig) {…}
	```
13. Implemente a função myStrcat que junta (concatena) a string orig à string dest. Poderá utilizar a função myStrcpy criada no exercício anterior.
	```C
	char *myStrcat(char *dest, char *orig){…} 
	```
14. Implemente a função troca.
	```C
	void troca (int *a, int *b) {…}
	```
	
15. Implemente a função strset que coloca o carácter ch em todas as posições da string str.
	```C
	char *strset(char *str, char ch) {…}
	```





# Exercícios de aritmética de apontadores (A2)

0.
1.  Preencha os valores em falta na Tabela 1 depois de executadas as seguintes instruções. Note que (sizeof(short int) == 2) e que (sizeof(void *) == 8) e assuma que o endereço de p2 é o próximo endereço livre a seguir ao endereço de p1.

```C
	unsigned short int x[2] = {0xABB9, 0xC0DD};
	unsigned short int *p1 = x;
	unsigned short int **p2 = &p1;
	(*p1)++;
	(*p2)++;
	(*p1)++;
```

| Endereço | Conteúdo | Identificador |
|:--------:|:--------:|:-------------:|
|    ...   |          |               |
|  0x100c  |          |      x[0]     |
|          |          |      x[1]     |
|    ...   |    ...   |       ...     |
|  0x2000  |          |      p1       |
|          |          |      p2       |
	


5. Indique justificando qual o output do seguinte código sem o executar:

    a)
    ```C
    int main () 
    {
      int numeros[] = {10, 20, 30};
      int * pNum = &numeros[0];
      printf("Valor = %d\n", *pNum);  
      pNum++;  
      printf("Valor = %d\n", *pNum);  
      pNum = pNum + 1;  
      printf("numero via ponteiro = %d\n", *pNum);  
      return 0; 
    }    
    ```
    b)
    ```C
    #include <stdio.h>   
    #define MAX 5    
    int main () 
    {    
      int numeros[MAX] = {10, 20, 30, 40, 50};    
      int* pNum = numeros;      
      while(pNum<=&numeros[MAX-1]) {      
        printf("numero via ponteiro = %d\n", *pNum);      
        pNum++;    
      }      
      return 0;  
    } 
    ```
    

1. **[A2]** Crie a declaração apropriada para as seguintes variáveis. Inicialize todos os vetores.
    
    a)	nome é uma cadeia com 10 caracteres
    
    b)	psa é um vetor de 10 ponteiros para caracteres
    
    c)	pstr é um ponteiro para um vetor de 10 caracteres


2. **[A2]** Considere as seguintes declarações e responda às questões justificando:

    ```C
    int * ptr;
    int ref[] = {1,2,3,4};
    ptr = &ref[0];
    ```
    a) ref é o endereço de quê?
    
    b) E ref+1?  
    
    c) Qual o valor de *ptr e *(ptr+2) ?



9. **[A2]** Seja o seguinte trecho de programa:
    ```C
    int i=3,j=5;
    int *p, *q;
    p = &i;
    q = &j;
    ```
    Qual é o valor das seguintes expressões ?
	  
    a) p == &i;
    
    b) *p - *q
    
    c) **&p
    
    d) 3* - *q/(*p)+7


10. **[A2]** Qual será a saída deste programa supondo que i ocupa o endereço 4094 na memória?
    ```C
    main() 
    {
      int i=5, *p;
      p = &i;
      printf(“%ld %d %d %d %d\n”, (long)p,*p+2,**&p,3**p,**&p+4);
    }
    ```

11. **[A2]** Se i e j são variáveis inteiras e p e q ponteiros para int, quais das seguintes expressões de atribuição são ilegais?
      
      a.	p = &i;
      
      b.	*q = &j;
      
      c.	p = &*&i;
      
      d.	i = (*&)j;
      
      e.	i = *&j;
      
      f.	i = *&*&j;
      
      g.	q = *p;
      
      h.	i = (*p)++ + *q


12. **[A2]** Qual é o resultado do seguinte programa?
    ```C
    #include <conio.h>
    #include <stdio.h>
    void main(){
      float vet[5] = {1.1,2.2,3.3,4.4,5.5};
      float *f;
      int i;
      f = vet;
      printf("contador/valor/valor/endereco/endereco");
      for(i = 0 ; i <= 4 ; i++){
        printf("\ni = %d",i);
        printf("   vet[%d] = %.1f",i, vet[i]);
        printf("   *(f + %d) = %.1f",i, *(f+i));
        printf("   &vet[%d] = %ld",i, (long)&vet[i]);
        printf("   (f + %d) = %ld",i, (long)f+i);
      }
    }
    ```
13. **[A2]** Assumindo que pulo[] é um vetor do tipo int, quais das seguintes expressões referenciam o valor do terceiro elemento da matriz?
    
    a.	*(pulo + 2)
    
    b.	*(pulo + 4)
    
    c.	pulo + 4
    
    d.	pulo + 2

14. **[A2]** Supor a declaração: int mat[4], *p, x; Quais expressões são válidas? Justifique:
    
    a.	p = mat + 1;
    
    b.	p = mat++;
    
    c.	p = ++mat;
    
    d.	x = (*mat)++;

15. **[A2]** O que fazem os seguintes programas:
    a)
    ```C
    #include <stdio.h>
    void main()
    {
      int vet[] = {4,9,13};
      int i;
      for(i=0;i<3;i++){
        printf("%d ",*(vet+i));
      }
    }
    ```
    b)
    ```C
    #include <stdio.h>
    void main()
    {
      int vet[] = {4,9,13};
      int i;
      for(i=0;i<3;i++){
        printf("%ld ",(long)vet+i);
      }
    }
    ```
    c)
    ```C
    #include <stdio.h>
    void main()
    {
      int vet[] = {4,9,13};
      int i;
      for(i=0;i<3;i++){
        printf("%d ", ++*(vet+i));
      }
    }
    ```
 16. **[A2]** O que faz o seguinte programa quando executado?
    
    a)    
    ```C
    #include <stdio.h>
    void main() 
    {
      int vet[] = {4,9,12};
      int i,*ptr;
      ptr = vet;
      for(i = 0 ; i < 3 ; i++) {
        printf("%d ",*ptr++);
      }
    }
    ```
    b)
    ```C
    #include <stdio.h>
    void main()
    {
      int vet[] = {4,9,12};
      int i,*ptr;
      ptr = vet;
      for(i = 0 ; i < 3 ; i++) {
        printf("%d ",(*ptr)++);
      }
    }
    ```

17. **[A2]** Seja vet um vetor de 4 elementos: TIPO vet[4]. Supor que depois da declaração, vet esteja armazenado no endereço de memória 4092 (ou seja, o endereço de vet[0]). Supor também que na máquina usada uma variável do tipo char ocupa 1 byte, do tipo int ocupa 2 bytes, do tipo float ocupa 4 bytes e do tipo double ocupa 8 bytes.

  Qual o valor de vet+1, vet+2 e vet+3 se:
  
    a.	vet for declarado como char?
    
    b.	vet for declarado como int?
    
    c.	vet for declarado como float?
    
    d.	vet for declarado como double?


x3. **[A2]** Implemente a função myStrlen. Esta função deverá retornar a diferença entre o primeiro endereço de memória da string e o último.
int myStrlen(char *s) {…}

x4. **[A2]** Identifique os erros nestas operações:
	
	```C
	char s[20] = “Ola”;
	s = “ole”
	s++
	s+1
	*s
	(*s)++
	s = s-2
	s < s+1
	s+1-s
	```
