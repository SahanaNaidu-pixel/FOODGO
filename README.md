# FoodGo — React + Vite food delivery app

Premium food delivery application built with React, Vite, Express, and PostgreSQL.

## Run
```bash
npm install
npm run dev
```
Open the local URL shown by Vite.

## Project modules
- **User:** sign up / sign in, browse the food catalog, manage a cart, and view order tracking.
- **Admin:** add and remove food catalog items from the Admin Panel.
- **Authentication and demo catalog data** are stored in the browser's Local Storage. This is for coursework demonstration only; credentials are not protected and this is not production authentication.

## Deploy the frontend to Vercel
### Vercel CLI
```bash
npm install
npm install --global vercel
vercel login
vercel
```
For a production deployment after the project is linked, run `vercel deploy --prod`.

### GitHub import
1. Push this project to your GitHub repository.
2. In Vercel, choose **Add New Project** and import the repository.
3. Keep the detected Vite settings: build command `npm run build`, output directory `dist`.
4. Deploy, then open the generated Vercel URL and verify signup, login, and both modules.

`vercel.json` routes app URLs to the Vite entry point. The frontend works with its built-in sample catalog on Vercel. The Express/PostgreSQL API is a separate service and is not deployed by this Vercel frontend configuration. If you deploy that API separately, set `VITE_API_URL` to its public base URL. Set `VITE_UPI_ID` and `VITE_UPI_NAME` in Vercel project environment variables if you want to configure the checkout QR code.

## PostgreSQL setup
1. In pgAdmin, create a database named `foodgo`.
2. Open `db/schema.sql` in pgAdmin's Query Tool and execute it.
3. Copy `.env.example` to `.env` and replace `YOUR_PASSWORD` with the PostgreSQL password for your local `postgres` user.
4. Start the API with `npm run server`, or start both API and frontend with `npm run dev:full`.

The API runs on `http://localhost:4000`. Check the connection at `http://localhost:4000/api/health`.

## Included
- Animated hero with floating food stickers
- Search and cuisine filters
- Restaurant and menu views
- Cart + LocalStorage persistence
- Checkout and scheduled delivery UI
- Animated order tracking
- User and Admin modules
- Dark/light mode
- Glassmorphism, gradients, hover motion and micro-interactions
- PostgreSQL-backed menu API with a local mock-data fallback when the API is unavailable
