# Welcome to my blog

I'm glad you are here. I plan to talk about GitHub Pages


package com.shankar.company;

import java.util.HashMap;

public class Main {

    public static void main(String[] args) {

        int arr[] = new int[] { 3, 3, 2, 1 };//Expected output =1

        boolean isVisited[] = new boolean[arr.length + 1];

        HashMap<Integer, Integer> nodeMap = new HashMap<Integer, Integer>();

        for (int i = 1; i < isVisited.length; i++) {
            nodeMap.put(i, arr[i - 1]);
        }
        int countSwap = 0;

        for (int k = 1; k <= nodeMap.size(); k++) {

            int nextNode;

            if (isVisited[k] == false) {
                isVisited[k] = true;

                if (k == nodeMap.get(k)) {
                    continue;
                } else {
                    int c = nodeMap.get(k);
                    while (!isVisited[c]) {

                        isVisited[c] = true;

                        nextNode = nodeMap.get(c);
                        c = nextNode;
                        ++countSwap;
                    }
                }
            }
        }

        System.out.println("swap count :" + countSwap);
    }
}

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



