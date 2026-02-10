# Use NodeJS 20 official image
FROM node:20

# Create non-root user (roboshop)
RUN useradd --system --home /app --shell /sbin/nologin roboshop

# Set working directory
WORKDIR /app

# Copy application code
COPY . /app

# Install dependencies
RUN npm install

# Change ownership to roboshop user
RUN chown -R roboshop:roboshop /app

# Switch to non-root user
USER roboshop

# Environment variables
ENV MONGO=true
ENV MONGO_URL="mongodb://mongodb:27017/catalogue"

# Expose catalogue port
EXPOSE 8080

# Start the application
CMD ["node", "server.js"]
