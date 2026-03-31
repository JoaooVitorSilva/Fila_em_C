# Fila Dinâmica com Lista Encadeada em C

Implementação de uma **fila** (estrutura FIFO — *First In, First Out*) utilizando **lista encadeada** alocada dinamicamente no heap em linguagem C.

---

## Estrutura de Dados

### `Nodo`
Representa cada elemento da fila.

| Campo      | Tipo           | Descrição                          |
|------------|----------------|------------------------------------|
| `valor`    | `int`          | Valor armazenado no nó             |
| `proximo`  | `struct Nodo*` | Ponteiro para o próximo nó         |

### `Fila`
Estrutura de controle da fila.

| Campo      | Tipo    | Descrição                          |
|------------|---------|------------------------------------|
| `inicio`   | `Nodo*` | Ponteiro para o primeiro elemento  |
| `fim`      | `Nodo*` | Ponteiro para o último elemento    |
| `tamanho`  | `int`   | Quantidade de elementos na fila    |

---

## Funções

### `void inicializar(Fila *f)`
Inicializa a fila, zerando todos os campos. Deve ser chamada antes de qualquer outra operação.

---

### `int enfileirar(Fila *f, int valor)`
Insere um novo elemento no **final** da fila (política FIFO).

- Aloca um novo `Nodo` no heap com `malloc`
- Retorna `1` em caso de sucesso
- Retorna `-1` se a alocação de memória falhar

---

### `int desenfileirar(Fila *f)`
Remove o elemento do **início** da fila e libera sua memória com `free`.

- Retorna `1` em caso de sucesso
- Retorna `0` se a fila estiver vazia

---

### `void imprimir(Fila *f)`
Percorre a fila do início ao fim e imprime todos os valores no terminal.

**Saída de exemplo:**
```
Fila: 10 20 30 40
```

---

### `void destruir(Fila *f)`
Libera toda a memória alocada, removendo todos os nós da fila. Chama `desenfileirar` repetidamente até a fila estar vazia.

---

## Como Compilar e Executar

```bash
gcc fila.c -o fila
./fila
```

---

## Saída Esperada

```
Fila: 10 20 30 40
Fila: 20 30 40
```

A primeira linha mostra a fila após inserir 10, 20, 30 e 40.  
A segunda linha mostra a fila após remover o primeiro elemento (10).

---

## Complexidade

| Operação        | Complexidade |
|-----------------|--------------|
| `enfileirar`    | O(1)         |
| `desenfileirar` | O(1)         |
| `imprimir`      | O(n)         |
| `destruir`      | O(n)         |

---

## Conceitos Aplicados

- Alocação dinâmica de memória (`malloc` / `free`)
- Estrutura de dados FIFO (Fila)
- Lista encadeada simples
- Ponteiros e structs em C
- Verificação de falha de alocação (`NULL check`)
