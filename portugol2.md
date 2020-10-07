Algoritmo "Sistema de Notas"

Var
// Seção de Declarações das variáveis
  TURMA, DISC : CARACTER
  NUMDISC, control1, control2, QTDALUN, QTDALUNFIN, QTDALUNAPROV, QTDALUNREPROV, QTDTOTALALUNO, AV1, AV2 : INTEIRO
  MEDALUN, MENORMED, MAIORMED, TOTALMED, MEDDISC, MEDGERALTUR: REAL

Inicio
// Seção de Comandos, procedimento, funções, operadores, etc...
escreval ("SISTEMA DE NOTAS")
escreval (" ")

    QTDALUN  <- 1

  escreval ("Digite o nome da turma:")
  leia (TURMA)
  escreval ("Digite o numero de disciplinas:")
  leia (NUMDISC)

  escreval ("'''''''''''''''''''''''''''''''''''''''")

  para control1 de 1 ate NUMDISC faca
      QTDALUNREPROV <- 0
      QTDALUNFIN <- 0
      QTDALUNAPROV <- 0
      MEDDISC <- 0
      TOTALMED <- 0
      MAIORMED <- 0
      MENORMED <- 10

      escreval ("Digite o nome da" ,control1, " disciplina :")
      leia (DISC)
      escreval (" ")
      escreval ("Digite quantidade de alunos na" ,control1, " disciplina:")
      leia (QTDALUN)
      QTDTOTALALUNO <- QTDTOTALALUNO + QTDALUN
      escreval (" ")


  para control2 de 1 ate QTDALUN faca
      escreval ("Digite nota AV1 do" ,control2, " aluno:")
      leia (AV1)
      escreval ("Digite nota AV2 DO" ,control2, " aluno:")
      leia (AV2)
      escreval (" ")
      MEDALUN <- (AV1 + AV2) / 2
      TOTALMED <- TOTALMED + MEDALUN

      //Media menor que 3
        se (MEDALUN < 3) entao
        escreval ("ALUNO REPROVADO POR MEDIA = " ,MEDALUN)
        escreval (" ")
        TOTALMED <- (MEDALUN)
        QTDALUNREPROV <- (QTDALUNREPROV) + 1
        se (MEDALUN < MENORMED) entao
        MENORMED <- MEDALUN
        fimse
        se (MEDALUN > MAIORMED) entao
        MAIORMED <- MEDALUN
        fimse
        fimse

      //Media maior ou igual a 3 e menor que 7
        se (MEDALUN >= 3) E (MEDALUN < 7) entao
        escreval ("ALUNO VAI REALIZAR PROVA FINAL, MEDIA = ",MEDALUN)
        escreval (" ")
        QTDALUNFIN <- (QTDALUNFIN) + 1
        se (MEDALUN < MENORMED) entao
        MENORMED <- MEDALUN
        fimse
        se (MEDALUN > MAIORMED) entao
        MAIORMED <- MEDALUN
        fimse
        fimse


      //Media maior ou igual a 7
        se (MEDALUN >= 7) entao
        escreval (" ALUNO APROVADO POR MEDIA = ", MEDALUN)
        escreval (" ")
        QTDALUNAPROV <- (QTDALUNAPROV) + 1
        se (MEDALUN < MENORMED) entao
        MENORMED <- MEDALUN
        fimse
        se (MEDALUN > MAIORMED) entao
        MAIORMED <- MEDALUN
        fimse
        fimse

 fimpara

        MEDDISC <- (TOTALMED / QTDALUN)
        MEDGERALTUR <- MEDGERALTUR + MEDDISC

      escreval ("++++++++++++++++++++++++++++++++++++++++++++++")
      escreval (" ")

      escreval ("\RESUMO DA DISCIPLINA/")
      escreval ("DISCIPLINA: ", DISC)
      escreval ("QUANTIDADE TOTAL DE ALUNOS: ", QTDALUN)
      escreval ("MÉDIA GERAL DA DISCIPLINA: ", MEDDISC)
      escreval ("MAIOR MEDIA DA DISCIPLINA: ", MAIORMED)
      escreval ("MENOR MÉDIA DA DISCIPLINA: ", MENORMED)
      escreval ("QTD ALUNOS REPROVADOS: ", QTDALUNREPROV)
      escreval ("QTD ALUNOS NA FINAL: ", QTDALUNFIN)
      escreval ("QTD ALUNOS APROVADOS: ", QTDALUNAPROV)

      escreval (" ")
      ESCREVAL ("++++++++++++++++++++++++++++++++++++++++++++++")
      ESCREVAL (" ")

fimpara

      MEDGERALTUR <- MEDGERALTUR / QTDTOTALALUNO

      escreval (" ")
      escreval ("+++++++++++++++++++++++++++++++++++++++++++++++")
      escreval (" ")

      escreval ("\RESUMO DA TURMA/")
      escreval ("TURMA: ", TURMA)
      escreval ("QUANTIDADE DE DISCIPLINAS: ", NUMDISC)
      escreval ("MEDIA GERAL DA TURMA: ", MEDGERALTUR)


Fimalgoritmo
