FROM python:3-alpine

WORKDIR /app

# Install system dependencies
RUN apk add --no-cache \
    build-base \
    libffi-dev \
    postgresql-dev \
    musl-dev \
    gcc \
    g++ \
    python3-dev \
    linux-headers

# Install Python deps
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

EXPOSE 8000

# Start FastAPI with hot reload
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
