# Crie um sistema que imprima um recibo de compras para o usuário. 
# O sistema vai perguntar a quantidade de itens diferentes e depois vai perguntar 
# qual o nome do item e a quantidade deste item. 
# No final o programa exibe o recibo juntamente com o valor final da compra. 

print("Bem vindo!")
quantidadeItens = float(input("Quantidade de itens diferentes: "))

totalDaCompra = 0
itens = []

i = 0
while i < quantidadeItens:
    nomeItem = input("Nome do item " + str(i + 1) + ": ")
    quantidadeItem = float(input("Quantidade do item " + str(i + 1) + ": "))
    precoUnitarioItem = float(input("Preço do item " + str(i + 1) + ": "))
    precoTotalItem = float(quantidadeItem * precoUnitarioItem)
    totalDaCompra += precoTotalItem
   
    listaItens = {
        "quantidade": quantidadeItem,
        "nome": nomeItem,
        "preco": precoTotalItem
    }   

    itens.append(listaItens)
    i += 1

print("================================")
print("           RECIBO")
print(" ")
print("  NOME | QUANTIDADE | VALOR")
print(" ")
for item in itens:
    print("   {} - {} - R${}".format(item["nome"], item["quantidade"], item["preco"]))
print(" ")
print("Total: R$" + str(totalDaCompra))
print("================================")