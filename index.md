# Welcome to my blog

I'm glad you are here. I plan to talk about GitHub Pages

public class Main {
    public static void main(String[] args) {

        int[] arr = {4, 3, 2, 1};
        System.out.println(" = " + minimumSwaps(arr));

        System.out.println(" ================================================================================ " );

        arr = new int[]{3, 3, 1, 2};
        System.out.println(" = " + minimumSwaps(arr));

        System.out.println(" ================================================================================ " );


        arr = new int[]{4, 4, 1, 2, 4};
        System.out.println(" = " + minimumSwaps(arr));

        System.out.println(" ================================================================================ " );

    }

    static int minimumSwaps(int[] arr) {
        int minIndex = 0;
        int min = arr[0];
        int swaps = 0;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] < arr[minIndex]) {
                min = arr[i];
                minIndex = i;
            }
        }

        if (minIndex != 0) {
            int temp = arr[minIndex];
            arr[minIndex] = arr[0];
            arr[0] = temp;
            swaps++;
        }

        for (int i = 1; i < arr.length; i++) {
            int pos = arr[i] - min;
            while (arr[i] != arr[pos]) {
                int temp = arr[i];
                arr[i] = arr[pos];
                arr[pos] = temp;
                swaps++;
                pos = arr[i] - min;
            }
        }

        return swaps;
    }
}



