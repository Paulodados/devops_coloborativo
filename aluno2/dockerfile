# Usar uma imagem base leve do Python
FROM python:3.9-slim

# Atualizar o sistema e instalar dependências necessárias
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Definir variáveis de ambiente
ENV PYTHONUNBUFFERED=1 \
    JUPYTER_PORT=8888

# Definir diretório de trabalho
WORKDIR /app

# Copiar requirements.txt e instalar pacotes
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Expor a porta do Jupyter
EXPOSE $JUPYTER_PORT

# Comando para iniciar o Jupyter Lab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]