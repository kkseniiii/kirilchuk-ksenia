# kirilchuk-ksenia
Determine which numbers among the first N Fibonacci numbers can be given in the form W^2-1 (1 less than a certain square).
import java.util.Scanner;
import java.lang.Math;

    /**
     *  class Fibonacci numbers
     *  @author Kirilchuk Ksenia
     */

    public class Fibonacci {

        static class Fib {
            private int num;
            private int val;
            Fib(int num, int val)
            {//клас чисел Фібоначчі і їх порядкових номерів
                this.num = num;
                this.val = val;
            }
        }
        public static void main(String[] args) {
            Fib [] arr;
            arr = new Fib[40];
            int first = 0,next = 1;
            for (int i = 1; i<=40; ++i)
            { //заповнення масиву числами Фіобначчі
                int sum = first + next;
                first = next;
                next = sum;
                arr[i-1] = new Fib (i, sum);
            }
            System.out.println("Введіть скільки перших чисел Фібоначчі хочете перевірити (менше 40)");
            Scanner scanner = new Scanner(System.in);
            int n = scanner.nextInt();
            for (int i = 0; i!=n; ++i)
            {
                if (Math.sqrt(arr[i].val+1) == (int)Math.sqrt(arr[i].val+1))
                {//перевірка чи корінь [число +1] є цілим
                    System.out.println("Число під номером "+arr[i].num+". "+ arr[i].val + " можна задати у формі " + Math.sqrt(arr[i].val+1) + "^2 - 1" );
                }
            }
            System.out.println("Усі використані числа Фібоначчі: ");
            for (int i = 0; i!=n; ++i)
            {
                System.out.print(arr[i].val+ ", ");
            }
        }
    }
