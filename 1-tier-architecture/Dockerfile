# Step 1: Use an official lightweight Python image
FROM python:3.11-slim

# Step 2: Set working directory inside container
WORKDIR /app

# Step 3: Copy requirements first to leverage Docker layer caching
COPY requirements.txt .

# Step 4: Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Step 5: Copy application code, static assets, and templates
COPY . .

# Step 6: Expose application port
EXPOSE 5000

# Step 7: Start Python app using a production WSGI server (Gunicorn)
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
