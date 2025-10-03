FROM mcr.microsoft.com/playwright:v1.55.0-noble

# Set working directory
WORKDIR /home/pwuser

# Install playwright globally
RUN npm install -g playwright@1.55.0

# Ensure correct ownership
RUN chown -R pwuser:pwuser /home/pwuser

# Switch to non-root user
USER pwuser

# Expose a port (Heroku ignores this, but good for local testing)
EXPOSE 3003

# Run server using Heroku's $PORT variable
CMD ["playwright", "run-server", "--port", "$PORT", "--host", "0.0.0.0"]
