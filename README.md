# FactoryVSSpringFramework
# 💳 Comparação entre Factory Pattern e Spring Framework para Processamento de Pagamentos

**Autores:** Ariane Sanga, Ellen Gonçalves

---

## 🧠 Introdução ao Problema

Em um sistema de e-commerce, o pagamento é uma parte crítica. O desafio foi criar uma solução com três métodos de pagamento: **Cartão de Crédito**, **PIX** e **PayPal**.

Criamos duas versões do sistema:

- Uma usando **Java puro com o padrão Factory**.
- Outra com **injeção de dependência utilizando o Spring Framework**.

Em ambos os casos, o tipo de pagamento é definido durante a construção do sistema (compile time), e não em tempo de execução.

---

## 💡 O que é Injeção de Dependência?

**Injeção de Dependência (Dependency Injection - DI)** é um padrão de design que reduz o acoplamento entre classes, promovendo:

- ✅ Menor acoplamento  
- ✅ Maior flexibilidade  
- ✅ Testes mais fáceis  
- ✅ Manutenção facilitada  

O Spring Framework é uma das ferramentas mais conhecidas que implementa esse padrão.

---

## 🛠️ Implementação em Java Puro (Factory Pattern)

### Interface `PaymentProcessor`

```java
package com.example.factory.service;

public interface PaymentProcessor {
    void process(double amount);
}

package com.example.factory.service;

public class CreditCardPaymentProcessor implements PaymentProcessor {
    @Override
    public void process(double amount) {
        System.out.println("[Processing payment with Credit Card]");
        System.out.println("Payment value: $ " + amount);
    }
}

package com.example.factory.service;

public class PixPaymentProcessor implements PaymentProcessor {
    @Override
    public void process(double amount) {
        System.out.println("[Processing payment with Pix]");
        System.out.println("Payment value: $ " + amount);
    }
}


