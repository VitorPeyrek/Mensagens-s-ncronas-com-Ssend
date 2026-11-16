# Mensagens-s-ncronas-com-Ssend
Mostrar, com dois processos, que `Ssend()` é um envio síncrono: a chamada só termina quando uma recepção correspondente foi iniciada.
## Como funciona

- O rank 1 espera `--atraso` segundos antes de chamar `Recv`.
- O rank 0 mede quanto tempo o `Ssend` demora para retornar, que deve ser
  aproximadamente igual ao atraso.
- O rank 1 devolve `2 * valor + 1` e o rank 0 confere o resultado.

## Execução

    mpiexec -n 2 python pratica4_mensagens_sincronas.py --valor 21 --atraso 1.0

Observação: exige exatamente 2 processos.
