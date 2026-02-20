/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package aqui_estan_los_18_ejercicios;

import java.util.Scanner;

/**
 *
 * @author Andrew
 */
public class Aqui_estan_los_18_ejercicios {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // Datos del login
        String usuario = "cami";
        String paso = "1234";

        Scanner escaner = new Scanner(System.in);

        while (true) {
            System.out.println("Inserte usuario:");
            String inputUsuario = escaner.nextLine();

            System.out.println("Escriba su contraseña:");
            String inputContrasena = escaner.nextLine();

            if (inputUsuario.equals(usuario) && inputContrasena.equals(paso)) {
                System.out.println("Ingreso correctamente\n");
                break;
            } else {
                System.out.println("Usuario o contraseña incorrectos, intente de nuevo\n");
            }
        }

        int menuu;
        double numero1, numero2, total;

        do {
            System.out.println("""
                Seleccione la operación:
                1. Par o impar
                2. Promedio de notas
                3. Calcular el IMC
                4. Salir
                """);
            menuu = escaner.nextInt();

            switch (menuu) {
                case 1 -> {
                    System.out.println("Ingrese un número:");
                    int caso1 = escaner.nextInt();
                    if (caso1 % 2 == 0) {
                        System.out.println("Es PAR\n");
                    } else {
                        System.out.println("Es IMPAR\n");
                    }
                }
                case 2 -> {
                    double porcentaje1 = 0.30;
                    double porcentaje2 = 0.20;
                    double porcentaje3 = 0.05;
                    double porcentaje4 = 0.05;
                    double porcentaje5 = 0.40;

                    // Nota 1 - TC
                    double nota1;
                    while (true) {
                        System.out.println("Coloque el TC (nota 1):");
                        nota1 = escaner.nextDouble();
                        if (nota1 >= 0 && nota1 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 2 - Pics
                    double nota2;
                    while (true) {
                        System.out.println("Coloque el Pics (nota 2):");
                        nota2 = escaner.nextDouble();
                        if (nota2 >= 0 && nota2 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 3 - Auto evaluación
                    double nota3;
                    while (true) {
                        System.out.println("Coloque la auto evaluación (nota 3):");
                        nota3 = escaner.nextDouble();
                        if (nota3 >= 0 && nota3 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 4 - Coevaluación
                    double nota4;
                    while (true) {
                        System.out.println("Coloque la coevaluación (nota 4):");
                        nota4 = escaner.nextDouble();
                        if (nota4 >= 0 && nota4 <= 5) {  
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 5 - Parcial
                    double nota5;
                    while (true) {
                        System.out.println("Coloque el parcial (nota 5):");
                        nota5 = escaner.nextDouble();
                        if (nota5 >= 0 && nota5 <= 5) {  
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Calcular promedio ponderado
                    double totalNota = (nota1 * porcentaje1)
                            + (nota2 * porcentaje2)
                            + (nota3 * porcentaje3)
                            + (nota4 * porcentaje4)
                            + (nota5 * porcentaje5);

                    System.out.println("\nSu nota final es: " + totalNota);

                    if (totalNota >= 3.0) {
                        System.out.println("¡Aprobó la materia!");
                    } else {
                        System.out.println("No aprobó, tiene que repetir el semestre :(");
                    }
                }
                case 3 -> {
                    double peso, altura, imc;

                    // Pedir peso
                    while (true) {
                        System.out.println("Ingrese su peso (kg):");
                        peso = escaner.nextDouble();
                        if (peso > 0) {
                            break;
                        } else {
                            System.out.println("El peso debe ser mayor a 0\n");
                        }
                    }

                    // Pedir altura
                    while (true) {
                        System.out.println("Ingrese su altura (metros):");
                        altura = escaner.nextDouble();
                        if (altura > 0) {
                            break;
                        } else {
                            System.out.println("La altura debe ser mayor a 0\n");
                        }
                    }

                    // Calcular IMC
                    imc = peso / (altura * altura);

                    System.out.println("\nSu IMC es: " + imc);

                    // Clasificación
                    if (imc < 18.5) {
                        System.out.println("Esta bajo peso");
                    } else if (imc >= 18.5 && imc <= 24.9) {
                        System.out.println("Esta en peso normal");
                    } else if (imc >= 25 && imc <= 29.9) {
                        System.out.println("Alerta: sobrepeso");
                    } else {
                        System.out.println("Obesidad");  
                    }
                }
                case 4 -> {
                    System.out.println("Saliendo...");
                }
                default -> System.out.println("Opción inválida\n");
            }

        } while (menuu != 4);  
    }
}
