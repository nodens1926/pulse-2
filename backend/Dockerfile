FROM python:3.10-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    gcc \
    g++ \
    wget \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN pip install https://github.com/explosion/spacy-models/releases/download/en_core_web_sm-3.7.1/en_core_web_sm-3.7.1-py3-none-any.whl

CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]
