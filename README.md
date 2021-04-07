
# Taller1
package com.example.com.example.taller;

import java.util.Scanner;

//Para transformar de numeros decimales a binarios se necesitan los 8 numeros claves 128, 64, 32, 16, 8, 4, 2, 1.
//El rango de valores serian de 0 a 255
public class Taller {
    public static Scanner input = new Scanner(System.in);
    public static void main(String[] args) {
       menu();


    }
    public static void menu(){
        System.out.println("[1]Transformar de decimal a binario");
        System.out.println("[2]Transformar de binario a decimal");
        System.out.println("[3]Salir");
        int opcion = ingresoMenu(1,3);
        switch (opcion){
            case 1:
                imprimirNumero8bits(convetirBinario8Bits(leerNumero()));
                break;
            case 2:
                break;



        }
    }
    public static int ingresoMenu(int limInferior, int limSuperior) {

        int n = limInferior - 1;
        do {
            try {
                n = input.nextInt();
            } catch (Exception e) {
                input.next();
                System.out.println("Numero invalido");
            }
            if (n < limInferior || n > limSuperior) {
                System.out.println("Ingresa una opcion valida: ");
            }
        } while (n < limInferior || n > limSuperior);
        return n;

    }

    public static int leerNumero() {
        int num = -1;
        do {
            try {
                System.out.println("Introduce el numero a transformar: ");
                num = input.nextInt();

            } catch (Exception e) {
                input.next();
                System.out.println("Introduce un numero valido: ");
            }
        } while (num<0 || num>255);

        return num;
    }
    public static int [] convetirBinario8Bits(int num) {
        int [] numero8bits = new int[8];
        int [] octetos = {128, 64, 32, 16, 8, 4, 2, 1};
        for (int i = 0; i < octetos.length; i++) {
            int resta = num-octetos[i];
            if (resta>=0){
                num = num - octetos[i];
                numero8bits[i]=1;
            }else if (resta<0){
                numero8bits[i]=0;
            }

        }

        return numero8bits;




    }

    public static void imprimirNumero8bits(int[] num8bits){
        for (int i = 0; i < num8bits.length; i++) {
            System.out.print(num8bits[i]);
        }

    }



}



![2021-04-07 10_29_38-](https://user-images.githubusercontent.com/70740296/113884412-f1084a00-978c-11eb-968a-c2e5b9b4e9a9.png)
![2021-04-07 10_30_04-](https://user-images.githubusercontent.com/70740296/113884566-109f7280-978d-11eb-8080-903d9347a653.png)
