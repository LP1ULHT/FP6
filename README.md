**UNIVERSIDADE LUSÓFONA DE HUMANIDADES E TECNOLOGIAS**

*Linguagens de Programação I - 2019/2020*

# Ficha de Exercícios - 6: Ponteiros - Extra

Na resolução destes exercícios deve ser utilizada a Linguagem de Programação C. Para além da correta implementação dos requisitos, tenha em conta os seguintes aspetos:

- O código apresentado deve ser bem indentado. 
- O código deve compilar sem erros ou *warnings* utilizando o *gcc* com as seguintes flags:
- `gcc -Wall -Wextra -Wpedantic -std=c99 -g exercicio1.c -o exercicio1`
- Tenha em atenção os nomes dados das variáveis, para que sejam indicadores daquilo que as mesmas vão conter.
- Evite o uso de constantes mágicas. 
- Evite duplicação de código. 
- Considere a implementação de funções para melhorar a legibilidade, evitar a duplicação e criar soluções mais genéricas.

1.	Implemente um programa que contenha duas variáveis x e y do tipo int e float, ambas inicializadas com o valor 5. Declare também dois apontadores px e py, que apontam para x e y respetivamente.

	Em seguida mostre o valor das variáveis e o seu endereço armazenado no respetivo apontador. Depois mostre o valor das mesmas variáveis incrementado em uma unidade.
	
	*Notas:*
	Transforme os endereços num long int para melhor compreensão dos resultados.

2.	Implemente um programa que mostre uma string no ecrã pela ordem em que está escrita e pela ordem contrária. Use somente duas variáveis (char str[100] e char *ptr)


3.	Implemente a função myStrlen. Esta função deverá retornar a diferença entre o primeiro endereço de memória da string e o último.
int myStrlen(char *s) {…}

4.	Identifique os erros nestas operações:
	
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

5.	Implemente a função myStrcpy que copia a string orig para a string dest.
	```C
	char *myStrcpy(char *dest, char *orig) {…}
	```
	
6.	Implemente a função myStrcat que junta (concatena) a string orig à string dest. Poderá utilizar a função myStrcpy criada no exercício anterior.
	```C
	char *myStrcat(char *dest, char *orig){…} 
	```
7.	

8.	Implemente a função troca.
	```C
	void troca (int *a, int *b) {…}
	```
	
9.	Implemente a função strset que coloca o carácter ch em todas as posições da string str.
	```C
	char *strset(char *str, char ch) {…}
	```

10.	Implemente um programa que some todos os números passados na linha de comando.

	Exemplo:
	```bash
	> Soma
	0
	> Soma 10 20 30
	60
	> Soma 10 20 30 -5
	55
	```
