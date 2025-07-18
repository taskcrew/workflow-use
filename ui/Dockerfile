FROM node:20

WORKDIR /app

# Copy package files first for better caching
COPY package.json ./

# Install dependencies with postinstall disabled
ENV NOYARNPOSTINSTALL=1
RUN npm install --no-audit --no-fund

# Copy the rest of the application
COPY . .

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]