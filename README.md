# Домашнее задание к занятию "Testability, авто-тесты, введение в ООП: объекты и методы"

## Case3
**CreditPaymentService.java**
```java
package Case3;

public class CreditPaymentService {
    public double calculate(double amount, int years, double annualRate) {
        double monthlyRate = annualRate / 12 / 100;
        int numberOfPayments = years * 12;

        double monthlyPayment = amount *
                (monthlyRate * Math.pow(1 + monthlyRate, numberOfPayments)) /
                (Math.pow(1 + monthlyRate, numberOfPayments) - 1);

        return Math.round(monthlyPayment * 100.0) / 100.0;
    }
}
```
**Main3.java**
```java
package Case3;

public class Main3 {
    public static void main(String[] args) {
        CreditPaymentService service = new CreditPaymentService();

        System.out.println("Ежемесячный платёж при сроке кредита 1 год: " + (service.calculate(1_000_000, 1, 9.99)));
        System.out.println("Ежемесячный платёж при сроке кредита 2 года: " + (service.calculate(1_000_000, 2, 9.99)));
        System.out.println("Ежемесячный платёж при сроке кредита 3 года: " + (service.calculate(1_000_000, 3, 9.99)));
    }
}
```

**Результат**
```
Ежемесячный платёж при сроке кредита 1 год: 87911.24
Ежемесячный платёж при сроке кредита 2 года: 46140.31
Ежемесячный платёж при сроке кредита 3 года: 32262.49
```

### Файлы с кодом можно посмотреть в [папке](https://github.com/AngryCFO/Testability/tree/main/src)

