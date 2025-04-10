Roteiro 1 :

1)  
	package main

import "fmt"

func parouimpar(n int) {
    if (n % 2 == 0){
        fmt.Println("Par")  
    }  else {
        fmt.Println("impar")
    }
    
} 

func main() {
  fmt.Println("Insira um valor: ")
  var numero int
  fmt.Scanln(&numero)
  parouimpar(numero)
}



2) 
	package main

import "fmt"

func Somaate(n int) int {
	var soma int
	for i := 1; i <= n; i++ {
		soma += i
	}
	return soma
}

func main() {
	var n int
	fmt.Println("Digite um numero: ")
	fmt.Scan(&n)
	fmt.Println(Somaate(n))
}
	

3) 
	package main

import "fmt"

func verificador(nota float64) {
     if nota >= 9 && nota <= 10 {
        fmt.Println("Excelente")
    } else if nota >= 7 && nota < 9 {
        fmt.Println("Bom")
    } else if nota >= 5 && nota < 7 {
        fmt.Println("Regular")
    } else if nota >= 3 && nota < 5 {
        fmt.Println("Ruim")
    } else if nota >= 0 && nota < 3 {
        fmt.Println("Muito Ruim")
    } else {
        fmt.Println("Nota inválida")
    }
        
}

func main() {
	var nota float64
	fmt.Println("Digite um numero: ")
	fmt.Scan(&nota)
	verificador(nota)
}

Roteiro 2:

1) 
	package main

import (
	"fmt"
)

var arr[6]int

func main() {
	arr[0] = 1
	arr[1] = 2
	arr[2] = 4
	arr[3] = 3
	arr[4] = 7
	arr[5] = 4
	
	fmt.Println(arr[0])
	fmt.Println(arr[1])
	fmt.Println(arr[2])
	fmt.Println(arr[3])
	fmt.Println(arr[4])
	fmt.Println(arr[5])
}

3) 
	package main

import (
	"fmt"
)

var arr[6]int

func main() {
	arr[0] = 1
	arr[1] = 2
	arr[2] = 4
	arr[3] = 3
	arr[4] = 7
	arr[5] = 4
	
	for i := 0; i < len(arr); i++{
	fmt.Println(arr[i])
	}
4) 
	package main

import (
	"fmt"
)

var arr[6]int

func main() {
	arr[0] = 1
	arr[1] = 2
	arr[2] = 4
	arr[3] = 3
	arr[4] = 7
	arr[5] = 4
	
	for v := range arr {
	fmt.Println(arr[v])
	}
}

5)
	package main

import "fmt"

func main() {
    var dados [3][2]string 

    for i := 0; i < 2; i++ {
        dados[0][i] = fmt.Sprintf("%d", i+1) // índice
        fmt.Print("Digite o RA: ")
        fmt.Scan(&dados[1][i])
        fmt.Print("Digite o nome: ")
        fmt.Scan(&dados[2][i])
    }

    fmt.Println("\n--- Dados dos alunos ---")
    for i := 0; i < 2; i++ {
        fmt.Println("Índice:", dados[0][i], "RA:", dados[1][i], "Nome:", dados[2][i])
    }
}

6)
	package main

import "fmt"

type Produto struct{
	nome string
	preco float64
	Quantidade int 
}
func main() {

	
p1 := Produto{
	nome: "Arroz",
	preco: 5.99,
	Quantidade: 10,
}
p2 := Produto{
		nome: "banana",
		preco: 9.99,
		Quantidade: 12,
	}
p3 := Produto{
		nome: "carne",
		preco: 59.99,
		Quantidade: 1,
	}

	fmt.Println("Produto:", p1.nome, "Preço:", p1.preco, "Quantidade:", p1.Quantidade)
	fmt.Println("Produto:", p2.nome, "Preço:", p2.preco, "Quantidade:", p2.Quantidade)
	fmt.Println("Produto:", p3.nome, "Preço:", p3.preco, "Quantidade:", p3.Quantidade)
}

Roteiro 3:

1) 
	package main

import "fmt"

 

func main() {
var b int = 42 
var p *int = &b
fmt.Println("Valor de b : ",b)
fmt.Println("Endereco de b : ",p)


}

2)
	package main

import "fmt"

 

func main() {
var b int = 42 
var p *int = &b
fmt.Println("Valor de b antes : ",b)
*p = 100
fmt.Println("O valor novo de b: ",b)


}

3) 
	package main

import "fmt"

func trocadevalores(a,b *int) {
     temp := *a
    *a = *b
    *b = temp
    
 }

func main() {
var a int = 42 
var b int = 100
fmt.Println("Valor de a: ",a, "Valor de b: ",b)
trocadevalores(&a,&b)
fmt.Println("Valor de a: ",a, "Valor de b: ",b)
}

4) 
	package main

import "fmt"

type Tarefa struct {
    id        int
    descricao string
    proxima   *Tarefa
}

func main() {
    
    t1 := &Tarefa{id: 1, descricao: "Estudar Go"}
    t2 := &Tarefa{id: 2, descricao: "Fazer exercícios"}
    t3 := &Tarefa{id: 3, descricao: "Descansar"}

   
    t1.proxima = t2
    t2.proxima = t3

    
    atual := t1
    for atual != nil {
        fmt.Println("ID:", atual.id, "Descrição:", atual.descricao)
        atual = atual.proxima
    }
}

Roteiro 4:

1) 

package main

import "fmt"

func palindromo(palavra string){
	// Cria uma "pilha" com os caracteres da palavra
	lista := []byte{}

	for i := 0; i < len(palavra); i++ {
		lista = append(lista, palavra[i]) // empilha caractere
	}

	reverso := ""

	// Desempilha os caracteres e forma a palavra ao contrário
	for i := len(lista) - 1; i >= 0; i-- {
		reverso += string(lista[i])
	}

	// Compara a palavra original com a invertida
	if palavra == reverso {
		fmt.Println("E um Palindromo")
	} else {
	    fmt.Println("Nao e um Palindromo")
	}
	
}

func main() {
	palindromo("arara")   // true
	palindromo("radar")   // true
	palindromo("banana")  // false
}
	
