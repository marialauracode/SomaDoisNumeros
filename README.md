# SomaDoisNumeros

import tkinter as tk

def calcularSoma():
    try:
        num1 = float(entrada1.get())
        num2 = float(entrada2.get())
        soma = num1 + num2
        label_resultado_soma.config(text=f"{soma}")

    except ValueError:
        label_resultado_soma.config(text="ERRO: Entradas inválidas")


def limparEntrada():
    entrada1.delete(0, tk.END)
    entrada2.delete(0, tk.END)
    label_resultado_soma.config(text="0")


window = tk.Tk()
window.geometry('300x300')
window.title("Soma de Dois Números")    

label_num1 = tk.Label(window, text="Número 1:")
label_num1.pack()
entrada1 = tk.Entry(window)
entrada1.pack(pady=5)

label_num2 = tk.Label(window, text="Número 2:")
label_num2.pack()
entrada2 = tk.Entry(window)
entrada2.pack(pady=5)

botao_calcular = tk.Button(window, text="Calcular", command=calcularSoma)
botao_calcular.pack(pady=5)

botao_limpar = tk.Button(window, text="Limpar", command=limparEntrada)
botao_limpar.pack(pady=5)

label_resultado = tk.Label(window, text="Resultado: ", fg="black")
label_resultado.pack(pady=2)

label_resultado_soma = tk.Label(window, text="0", fg="red")
label_resultado_soma.pack()

window.mainloop()
