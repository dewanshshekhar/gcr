# ONDC Global Catalog Registry (GCR)

A modern, efficient solution for managing product catalogs in the Open Network for Digital Commerce (ONDC) ecosystem.

## Overview

The Global Catalog Registry (GCR) is designed to solve the NxN integration problem in ONDC by providing a centralized catalog system. This reduces complexity from NxN to N+N, making the system more efficient and scalable.

### Key Features

- 🔍 Fast and efficient product search
- 🔄 Real-time catalog updates
- 💾 Redis caching for improved performance
- 🔌 Seamless integration with Buyer Apps
- 📊 Consistent product data schema
- 🖼️ Media storage with BunnyCDN

## Tech Stack

- **Frontend**: Next.js 14 with TypeScript
- **Styling**: Tailwind CSS
- **Backend**: Next.js API Routes
- **Database**: MongoDB with Prisma ORM
- **Caching**: Redis
- **Storage**: BunnyCDN Storage & CDN
- **AI Integration**: Groq for search optimization and recommendations

## Getting Started

### Prerequisites

- Node.js 18.x or later
- Redis server
- MongoDB database (local or Atlas)
- BunnyCDN account with Storage Zone and Pull Zone
- Groq API key

### Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
DATABASE_URL="mongodb+srv://username:password@cluster.mongodb.net/ondc_gcr?retryWrites=true&w=majority"
REDIS_URL="redis://localhost:6379"
BUNNYCDN_STORAGE_ZONE_NAME="your-storage-zone-name"
BUNNYCDN_STORAGE_PASSWORD="your-storage-password"
BUNNYCDN_PULL_ZONE_URL="https://your-pull-zone.b-cdn.net"
GROQ_API_KEY="your_groq_api_key"
```

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ondc-gcr-project.git
   cd ondc-gcr-project
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up the database:
   ```bash
   npx prisma generate
   npx prisma db push
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:3000`.

## Project Structure

```
📂 ondc-gcr-project
├── 📂 src
│   ├── 📂 app
│   │   ├── 📂 api
│   │   │   ├── search
│   │   │   │   └── route.ts
│   │   │   └── upload
│   │   │       └── route.ts
│   │   └── page.tsx
│   ├── 📂 components
│   │   ├── SearchBar.tsx
│   │   ├── ProductList.tsx
│   │   └── AdapterLayer.tsx
│   └── 📂 lib
│       ├── redis.ts
│       ├── prisma.ts
│       └── bunnycdn.ts
├── prisma
│   └── schema.prisma
└── package.json
```

## API Endpoints

### Search Products
- **Endpoint**: `/api/search`
- **Method**: GET
- **Query Parameters**:
  - `q`: Search query string
- **Response**: Array of products matching the search criteria

### Upload File
- **Endpoint**: `/api/upload`
- **Method**: POST
- **Content-Type**: multipart/form-data
- **Body**:
  - `file`: The file to upload
- **Response**: Object containing the uploaded file URL

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- ONDC Network
- Next.js team
- Redis team
- BunnyCDN team
- Groq team
