# campeonatoo
package campeonato;

import java.util.Scanner;

public class Campeonato {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
      
        Scanner entrada = new Scanner(System.in);

        System.out.println("Cuanto equipos son");
        int equipos = entrada.nextInt();

        int[] goles_a_favor = new int[equipos];
        int[] goles_en_contra = new int[equipos];
        int[] puntos = new int[equipos];

        for (int i = 0; i < equipos; i++) {
            goles_a_favor[i] = 0;
            goles_en_contra[i] = 0;
            puntos[i] = 0;
        }

        for (int i = 0; i < equipos; i++) {
            for (int j = 0; j < equipos; j++) {
                int resultado1 = (int) (Math.random() * 10);
                int resultado2 = (int) (Math.random() * 10);

                if (resultado1 > resultado2) {

                    goles_a_favor[i] = (goles_a_favor[i]) + resultado1;
                    goles_en_contra[i] = (goles_en_contra[i]) + resultado2;
                    goles_a_favor[j] = (goles_a_favor[j]) + resultado2;
                    goles_en_contra[j] = (goles_en_contra[j]) + resultado1;
                    puntos[i] = (puntos[i]) + 3;
                } else if (resultado2 > resultado1) {

                    goles_a_favor[j] = (goles_a_favor[j]) + resultado2;
                    goles_en_contra[j] = (goles_en_contra[j]) + resultado1;
                    goles_a_favor[i] = (goles_a_favor[i]) + resultado1;
                    goles_en_contra[i] = (goles_en_contra[i]) + resultado2;
                    puntos[j] = (puntos[j]) + 3;
                } else {

                    goles_a_favor[i] = (goles_a_favor[i]) + resultado1;
                    goles_a_favor[j] = (goles_a_favor[j]) + resultado2;
                    goles_en_contra[i] = (goles_en_contra[i]) + resultado2;
                    goles_en_contra[j] = (goles_en_contra[j]) + resultado1;
                    puntos[i] = (puntos[i]) + 1;
                    puntos[j] = (puntos[j]) + 1;
                }

            }
        }
        
       for(int i=0 ; i<equipos;i++)
           System.out.println("equipo :"+(i+1)+" Goles a favor : "+goles_a_favor[i]+" Goles en contra : "+goles_en_contra[i]+" puntos: "+puntos[i]);

    }

}
