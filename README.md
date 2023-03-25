# Traductor_Simple [1 digito]
 Analizador sintatico simple que evalúa expresiones aritméticas en notación infija.
 Este código solo analiza expresiones aritméticas simples y puede producir resultados inesperados para expresiones más complejas o malformadas. 
 También se espera que la entrada sea una secuencia de caracteres que representen una expresión aritmética en notación infija, lo que limita su utilidad en la práctica.
 
 Gramatica usada en el programa.
 
 expr -> expr + term
 expr -> expr - term
 term -> term * factor
 term -> term / factor
 factor -> 0|1|2|3|4|5|6|7|8|9
 
La clase Parser tiene un campo estático lookahead que almacena el siguiente carácter que se leerá de la entrada.
El constructor de Parser inicializa lookahead leyendo el primer carácter de la entrada del sistema estándar de entrada (System.in.read()).
El método expr() analiza la expresión. Comienza llamando al método term() y luego entra en un ciclo que analiza los siguientes caracteres de la entrada en busca de operadores + o -. Si se encuentra un operador + o -, el analizador consume el carácter y llama a term() nuevamente. Si no se encuentra un operador, el ciclo termina.
El método term() es similar a expr(), pero busca operadores * o /.
El método factor() analiza un factor de la expresión. Si el siguiente carácter es un dígito, se escribe en la salida y se consume el carácter. De lo contrario, se genera una excepción de error de sintaxis.
El método match() comprueba si el siguiente carácter es igual al carácter esperado. Si es así, consume el carácter y actualiza lookahead. De lo contrario, se genera una excepción de error de sintaxis.
