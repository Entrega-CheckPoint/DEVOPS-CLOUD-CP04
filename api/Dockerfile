FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

ENV MONGO_URI="mongodb://mongo:27017"
ENV OLLAMA_URL="http://ollama:11434/api/generate"

COPY . .

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]