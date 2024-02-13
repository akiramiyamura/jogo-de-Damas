# jogo-de-Damas
Jogo de Damas
class Tabuleiro:
    def __init__(self):
        self.tabuleiro = [
            [' ', 'o', ' ', 'o', ' ', 'o', ' ', 'o'],
            ['o', ' ', 'o', ' ', 'o', ' ', 'o', ' '],
            [' ', 'o', ' ', 'o', ' ', 'o', ' ', 'o'],
            [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
            [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
            ['x', ' ', 'x', ' ', 'x', ' ', 'x', ' '],
            [' ', 'x', ' ', 'x', ' ', 'x', ' ', 'x'],
            ['x', ' ', 'x', ' ', 'x', ' ', 'x', ' ']
        ]

    def mostrar_tabuleiro(self):
        for linha in self.tabuleiro:
            print(' | '.join(linha))
            print('---------------------------------')

    def fazer_movimento(self, linha_origem, coluna_origem, linha_destino, coluna_destino):
        self.tabuleiro[linha_destino][coluna_destino] = self.tabuleiro[linha_origem][coluna_origem]
        self.tabuleiro[linha_origem][coluna_origem] = ' '

if __name__ == "__main__":
    tabuleiro = Tabuleiro()
    tabuleiro.mostrar_tabuleiro()

    while True:
        linha_origem = int(input("Digite a linha da peça que você quer mover: "))
        coluna_origem = int(input("Digite a coluna da peça que você quer mover: "))
        linha_destino = int(input("Digite a linha para onde você quer mover a peça: "))
        coluna_destino = int(input("Digite a coluna para onde você quer mover a peça: "))

        tabuleiro.fazer_movimento(linha_origem, coluna_origem, linha_destino, coluna_destino)
        tabuleiro.mostrar_tabuleiro()
