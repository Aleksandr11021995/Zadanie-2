// В методе SaleStats, изменяем тип продаж с int на long
public class SaleStats {
    private long[] sales;

    public SaleStats(long[] sales) {
        this.sales = sales;
    }

    // Далее остальные методы, в которых также меняем тип int на long
}

// В классе Main, обновляем тестовые данные и демонстрацию работы
public class Main {
    public static void main(String[] args) {
        long[] sales = {10, 5, 8, 12, 7};
        SaleStats stats = new SaleStats(sales);

        System.out.println("Total sales: " + stats.getTotalSales());
        System.out.println("Average sales: " + stats.getAverageSales());
    }
}
// В методе SaleStats, добавляем новый метод getTrimmedMeanSales
public class SaleStats {
    private long[] sales;

    public SaleStats(long[] sales) {
        this.sales = sales;
    }

    public long getTotalSales() {
        long total = 0;
        for (long sale : sales) {
            total += sale;
        }
        return total;
    }

    public double getAverageSales() {
        return (double) getTotalSales() / sales.length;
    }

    // Новый метод расчёта обрезанного среднего
    public double getTrimmedMeanSales() {
        int trimmedLength = sales.length - 2;
        long sum = 0;
        long min = sales[0];
        long max = sales[0];
        for (long sale : sales) {
            if (sale < min) {
                min = sale;
            }
            if (sale > max) {
                max = sale;
            }
            sum += sale;
        }
        sum -= min + max;
        return (double) sum / trimmedLength;
    }
}

// В классе Main, добавляем демонстрацию работы нового метода
public class Main {
    public static void main(String[] args) {
        long[] sales = {10, 5, 8, 12, 7};
        SaleStats stats = new SaleStats(sales);

        System.out.println("Total sales: " + stats.getTotalSales());
        System.out.println("Average sales: " + stats.getAverageSales());
        System.out.println("Trimmed mean sales: " + stats.getTrimmedMeanSales());
    }
}
