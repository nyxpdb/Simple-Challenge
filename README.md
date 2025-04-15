
# Explicação do Algoritmo `nextPermutation`

Esse algoritmo serve para **calcular a próxima permutação lexicográfica** de um array de inteiros.

Se já estivermos na maior permutação possível (tipo `[3, 2, 1]`), ele volta pra menor (`[1, 2, 3]`).

---

## 🧠 Passo a passo

### 1. Achar o ponto de virada

```java
int i = nums.length - 1;

while (i > 0 && nums[i - 1] >= nums[i]) {
    i--;
}
```

Aqui estamos procurando o primeiro número (da direita pra esquerda) que **quebra a ordem crescente**.  
Esse ponto é onde podemos trocar algo pra fazer uma permutação maior.

---

### 2. Verificar se o array é totalmente decrescente

```java
if (i == 0) {
    reverse(nums, 0, nums.length - 1);
    return;
}
```

Se não acharmos nenhum número que quebre a ordem (`i == 0`), significa que o array está **em ordem decrescente**, ou seja, na última permutação.  
A solução nesse caso é simplesmente **inverter tudo** para voltar à menor permutação.

---

### 3. Achar o menor número maior que `nums[i - 1]`

```java
int j = nums.length - 1;

while (j >= i && nums[j] <= nums[i - 1]) {
    j--;
}
```

Aqui procuramos da direita pra esquerda o menor número que seja **maior que `nums[i - 1]`**, pra trocar com ele.

---

### 4. Trocar os valores

```java
swap(nums, i - 1, j);
```

Fazemos a troca entre `nums[i - 1]` e `nums[j]`.

---

### 5. Inverter o final

```java
reverse(nums, i, nums.length - 1);
```

Por fim, invertemos todos os números **à direita do ponto de virada** pra garantir que estamos pegando a menor sequência possível depois da troca.

---

## 💡 Exemplo prático

Dado o array `[1, 2, 3]`:

1. `i = 2`, pois `2 < 3`
2. `j = 2`, pois `3 > 2`
3. Troca `2` com `3` → `[1, 3, 2]`
4. Inverte o final (só o 2) → continua `[1, 3, 2]`

---

## 🔁 Métodos auxiliares

### Swap

```java
private void swap(int[] nums, int i, int j) {
    int temp = nums[i];
    nums[i] = nums[j];
    nums[j] = temp;
}
```

### Reverse

```java
private void reverse(int[] nums, int start, int end) {
    while (start < end) {
        int temp = nums[start];
        nums[start] = nums[end];
        nums[end] = temp;
        start++;
        end--;
    }
}
```
