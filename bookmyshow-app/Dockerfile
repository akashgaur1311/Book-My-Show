# =========================
# Build Stage
# =========================
FROM node:23-alpine AS build

WORKDIR /app

# Copy package files
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Copy application
COPY . .

# Build React application
RUN npm run build


# =========================
# Production Stage
# =========================
FROM nginx:alpine

# Copy React build to nginx
COPY --from=build /app/build /usr/share/nginx/html

# Expose nginx port
EXPOSE 3000

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
