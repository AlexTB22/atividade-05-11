import matplotlib.pyplot as plt
#1
semana = [1, 2, 3, 4, 5, 6, 7]
estoque = [100, 95, 110, 105, 120, 115, 130]
#2
produtos = ['Teclado', 'Mouse', 'Monitor', 'Webcam']
quantidades = [50, 75, 30, 60]
#3
valores = [15000, 8000, 5000]
categorias = ['Eletrônicos', 'Vestuário', 'Alimentos']
soma = sum(valores)
explode = (0.05, 0, 0)
porcentos = [v / soma for v in valores]
CatVal = [ categorias for categorias in valores]
#4
precos = [50, 120, 300, 80, 20]
estoque1 = [80, 25, 10, 70, 150]

fig, axs = plt.subplots(2, 2, figsize=(10, 6))

# 1
axs[0, 0].plot(semana, estoque)
axs[0, 0].set_title("1. Tendência de Estoque Diário")
axs[0, 0].set_xlabel("Dias")
axs[0, 0].set_ylabel("Estoque")

# 2
axs[0, 1].bar(produtos, quantidades)
axs[0, 1].set_title("2. Comparação de Produtos")
axs[0, 1].set_xlabel("Produtos")
axs[0, 1].set_ylabel("quantidades")

# 3
axs[1, 0].pie(porcentos, 
        explode=explode, 
        labels=categorias, 
        autopct='%1.1f%%',
        shadow=True, 
        startangle=90,
        wedgeprops={"edgecolor":"black", 'linewidth': 1, 'antialiased': True})
axs[1, 0].axis('equal')  
axs[1, 0].set_title("3. Proporção de Categorias")
axs[1, 0].legend(CatVal, title="Categorias", loc="center left", bbox_to_anchor=(1, 0, 0.5, 1))

# 4
axs[1, 1].scatter(precos, estoque1, color='royalblue', s=100, alpha=0.8, edgecolors='black')
axs[1, 1].set_title("4. Preço vs. Quantidade")
axs[1, 1].set_xlabel("Preço do Produto (R$)")
axs[1, 1].set_ylabel("Quantidade em Estoque")

plt.tight_layout()
plt.show()
# atividade-05-11
