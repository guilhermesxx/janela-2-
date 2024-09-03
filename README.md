import tkinter as tk

janela = tk.Tk()
janela.title("Calculadora")
janela.geometry("300x300")
janela.configure(bg="lightblue")

tk.Label(janela, text="Número 1:", bg="lightblue").pack()
num1 = tk.Entry(janela)
num1.pack()

tk.Label(janela, text="Número 2:", bg="lightblue").pack()
num2 = tk.Entry(janela)
num2.pack()

def mostrar_resultado(resultado):
    janela_resultado = tk.Toplevel(janela)
    janela_resultado.title("Resultado")
    tk.Label(janela_resultado, text=f"Resultado: {resultado}").pack()

def adicionar():
    resultado = float(num1.get()) + float(num2.get())
    mostrar_resultado(resultado)

def subtrair():
    resultado = float(num1.get()) - float(num2.get())
    mostrar_resultado(resultado)

def multiplicar():
    resultado = float(num1.get()) * float(num2.get())
    mostrar_resultado(resultado)

def dividir():
    if float(num2.get()) != 0:
        resultado = float(num1.get()) / float(num2.get())
    else:
        resultado = "Erro: Divisão por zero"
    mostrar_resultado(resultado)

tk.Button(janela, text="Adicionar", command=adicionar).pack()
tk.Button(janela, text="Subtrair", command=subtrair).pack()
tk.Button(janela, text="Multiplicar", command=multiplicar).pack()
tk.Button(janela, text="Dividir", command=dividir).pack()

janela.mainloop()
