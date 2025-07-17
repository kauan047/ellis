# 1. Escolha da Imagem Base
# Usamos uma imagem "slim" que é um bom meio-termo entre tamanho e compatibilidade.
FROM python:3.11-slim-bullseye

# 2. Definir o diretório de trabalho dentro do contêiner
WORKDIR /app

# 3. Copiar o arquivo de dependências
# Isso é feito separadamente para aproveitar o cache de camadas do Docker.
COPY requirements.txt .

# 4. Instalar as dependências
RUN pip install --no-cache-dir --upgrade -r requirements.txt

# 5. Copiar o restante do código da aplicação
COPY . .

# 6. Expor a porta em que a aplicação será executada
EXPOSE 8000

# 7. Comando para executar a aplicação quando o contêiner iniciar
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]