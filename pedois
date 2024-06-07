venda = None

def iniciar_venda():
    global venda
    if venda is not None:
        print("Não é possível iniciar uma nova venda com outra em andamento.")
        return
    
    venda = {
        'cliente': {
            'nome': input("Nome do cliente: "),
            'email': input("Email do cliente: "),
            'cpf': input("CPF do cliente: ")
        },
        'endereco_entrega': {
            'logradouro': input("Logradouro"),
            'cidade': input("Cidade: "),
            'bairro': input("Bairro: "),
            'estado': input("Estado: "),
            'cep': input("CEP: ")
        },
        'produtos': []
    }
    print("Venda iniciada, adicione mais produto ou encerre")

def adicionar_produto():
    global venda
    if venda is None:
        print("Nenhuma venda ativa")
        return

    produto = {
        'nome': input("Nome do produto: "),
        'preco': float(input("Preço: R$")),
        'quantidade': int(input("Quantidade: "))
    }
    venda['produtos'].append(produto)
    print("Produto adicionado")

def fechar_venda():
    global venda
    if venda is None:
        print("Nenhuma venda ativa")
        return
    
    venda['forma_pagamento'] = input("Forma de pagamento: ")
    
    print("\nDetalhes da Venda:")
    print(f"Cliente: {venda['cliente']['nome']}")
    print(f"Email: {venda['cliente']['email']}")
    print(f"CPF: {venda['cliente']['cpf']}")
    print("Endereço de Entrega:")
    print(f"  Logradouro: {venda['endereco_entrega']['logradouro']}")
    print(f"  Cidade: {venda['endereco_entrega']['cidade']}")
    print(f"  Bairro: {venda['endereco_entrega']['bairro']}")
    print(f"  Estado: {venda['endereco_entrega']['estado']}")
    print(f"  CEP: {venda['endereco_entrega']['cep']}")
    
    print("\nProdutos:")
    valor_total = 0
    for produto in venda['produtos']:
        subtotal = produto['preco'] * produto['quantidade']
        print(f"  - {produto['nome']}: R${produto['preco']:.2f} x {produto['quantidade']} = R${subtotal:.2f}")
        valor_total += subtotal
    
    print(f"\nForma de Pagamento: {venda['forma_pagamento']}")
    print(f"Valor Total: R${valor_total:.2f}")
    
    venda = None
    print("Venda fechada")

def main():
    global venda
    venda = None

    while True:
        print("\nMenu:")
        print("1. Iniciar a venda")
        print("2. Adicionar produto na venda")
        print("3. Fechar venda atual")
        print("4. SAIR")
        
        opcao = input("Escolha uma opção: ")
        
        if opcao == '1':
            iniciar_venda()
        elif opcao == '2':
            adicionar_produto()
        elif opcao == '3':
            fechar_venda()
        elif opcao == '4':
            print("LOGOUT...")
            break
        else:
            print("Opção inexistente...")

if __name__ == "__main__":
    main()
