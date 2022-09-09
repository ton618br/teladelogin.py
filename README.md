# teladelogin.py
uma tela de login feita em python
====================================================================================
from optparse import Values
import PySimpleGUI as sg

layout = [
    [sg.Text('Usuario')],
    [sg.Input(key='usuario')],
    [sg.Text('Senha')],
    [sg.Input(key='senha')],
    [sg.Button('Login')],
    [sg.Text('',key='mensagem')],
    

]

window = sg.Window('Login',layout=layout)

while True:
    event, Values = window.read()
    if event == sg.WIN_CLOSED:
        break
    elif event == 'Login':
        
        senha_correta = '123456'
        usuario_correto = 'andre'

        usuario = Values['usuario']
        senha = Values['senha']

        if senha == senha_correta and usuario == usuario_correto:
            window['mensagem'].update('Login feito com sucesso')
        else:
            window['mensagem'].update('senha ou usuario incorreto')
