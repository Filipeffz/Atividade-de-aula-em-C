#include <stdio.h>
int main(void)
{
    int a, b, c, d, e, f;
    long contador = 0;
    const long TOTAL = 50063860L;
    for (a = 1; a <= 55; a++)
        for (b = a + 1; b <= 56; b++)
            for (c = b + 1; c <= 57; c++)
                for (d = c + 1; d <= 58; d++)
                    for (e = d + 1; e <= 59; e++)
                        for (f = e + 1; f <= 60; f++)
                        {
                            contador++;
                            if (contador <= 20 || contador > TOTAL - 5)
                                printf("%8ld: %02d %02d %02d %02d %02d %02d\n",
                                contador, a, b, c, d, e, f);
                            else if (contador % 10000000L == 0)
                                printf("%8ld: %02d %02d %02d %02d %02d %02d (progresso)\n",
                                contador, a, b, c, d, e, f);
                        }
    printf("\nTotal de combinacoes geradas: %ld\n", contador);
    printf("Valor esperado C(60,6)......: %ld\n", TOTAL);
    printf("Conferencia: %s\n", contador == TOTAL ? "OK" : "ERRO");
    return 0;
}
