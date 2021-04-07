# Hello-World
package com.example.com.example.taller;

import java.util.Scanner;

//Para transformar de numeros decimales a binarios se necesitan los 8 numeros claves 128, 64, 32, 16, 8, 4, 2, 1.
//El rango de valores serian de 0 a 255


public class Taller {
    public static Scanner input = new Scanner(System.in);
    public static void main(String[] args) {
//        menu();
        leerNumero();

    }
    public static void menu(){
        System.out.println("[1]Transformar de decimal a binario");
        System.out.println("[2]Transformar de binario a decimal");
        System.out.println("[3]Salir");
        int opcion = ingresoMenu(1,3);
        switch (opcion){
            case 1:


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

}
