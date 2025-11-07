FROM public.ecr.aws/lambda/python:3.11

WORKDIR /var/task

# Install system tools
RUN yum install -y gcc make rust cargo && \
    python3.11 -m pip install --upgrade pip setuptools wheel

# Copy requirements and install them directly
COPY req.txt .
RUN python3.11 -m pip install --no-cache-dir -r req.txt

# Copy application code
COPY . .

# Lambda entrypoint
CMD ["app.lambda_handler"]