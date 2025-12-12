# js  Primeiro-array2
Cria um array interno com elementos diversos 
class Fila {
  // O array interno é privado (convenção com "_")
  #itens;

  constructor() {
    this.#itens = [];
  }

  // Verifica se a fila está vazia
  isEmpty() {
    return this.#itens.length === 0;
  }

  // Retorna o elemento da frente sem remover
  peek() {
    if (this.isEmpty()) {
      return null; // ou pode lançar erro
    }
    return this.#itens[0];
  }

  // Remove e retorna o elemento da frente
  dequeue() {
    if (this.isEmpty()) {
      return null; // ou pode lançar erro
    }
    return this.#itens.shift(); // shift remove o primeiro elemento
  }

  // Adiciona um elemento no final
  enqueue(item) {
    this.#itens.push(item);
  }
}

// Exemplo de uso:
const fila = new Fila();
fila.enqueue("A");
fila.enqueue("B");
fila.enqueue("C");

console.log(fila.peek());   // A
console.log(fila.dequeue()); // A
console.log(fila.isEmpty()); // false
console.log(fila.dequeue()); // B
console.log(fila.dequeue()); // C
console.log(fila.isEmpty()); // true
