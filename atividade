import random

class JogoDaVelha:
    def __init__(self):
        self.tabuleiro = [['.' for _ in range(3)] for _ in range(3)]
        self.jogador_atual = 'X'

    def imprimir_tabuleiro(self):
        print("  1 2 3")
        for i in range(3):
            print(chr(ord('A') + i), end=" ")
            print(" ".join(self.tabuleiro[i]))

    def verificar_vitoria(self, jogador):
        for i in range(3):
            if self.tabuleiro[i][0] == self.tabuleiro[i][1] == self.tabuleiro[i][2] == jogador:
                return True
            if self.tabuleiro[0][i] == self.tabuleiro[1][i] == self.tabuleiro[2][i] == jogador:
                return True
        if self.tabuleiro[0][0] == self.tabuleiro[1][1] == self.tabuleiro[2][2] == jogador:
            return True
        if self.tabuleiro[0][2] == self.tabuleiro[1][1] == self.tabuleiro[2][0] == jogador:
            return True
        return False

    def obter_movimento(self):
        while True:
            movimento = input("Seu movimento (ex: A1): ").upper()
            if len(movimento) == 2 and movimento[0] in 'ABC' and movimento[1] in '123':
                linha = ord(movimento[0]) - ord('A')
                coluna = int(movimento[1]) - 1
                if self.tabuleiro[linha][coluna] == '.':
                    return linha, coluna
            print("Movimento inválido. Tente novamente.")

    def movimento_maquina(self):
        while True:
            linha = random.randint(0, 2)
            coluna = random.randint(0, 2)
            if self.tabuleiro[linha][coluna] == '.':
                return linha, coluna

    def jogar(self):
        print("Vamos jogar Jogo da Velha!")
        self.imprimir_tabuleiro()

        for _ in range(9):
            if self.jogador_atual == 'X':
                linha, coluna = self.obter_movimento()
            else:
                linha, coluna = self.movimento_maquina()
                print("A máquina jogou:", chr(linha + ord('A')) + str(coluna + 1))

            self.tabuleiro[linha][coluna] = self.jogador_atual
            self.imprimir_tabuleiro()
            
            if self.verificar_vitoria(self.jogador_atual):
                if self.jogador_atual == 'X':
                    print("Parabéns! Você venceu!")
                else:
                    print("A máquina venceu!")
                break

            self.jogador_atual = 'O' if self.jogador_atual == 'X' else 'X'
        else:
            print("Empate!")

# Executar o jogo
jogo = JogoDaVelha()
jogo.jogar()
