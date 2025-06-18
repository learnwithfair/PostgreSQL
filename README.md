
[![Youtube][youtube-shield]][youtube-url]
[![Facebook][facebook-shield]][facebook-url]
[![Instagram][instagram-shield]][instagram-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

Thanks for visiting my GitHub account!

# PostgreSQL Installation Guide (Windows)

> This guide provides step-by-step instructions to install PostgreSQL on a Windows system, including optional setup for development with Node.js, Prisma, and Next.js.


## Step 1: Download PostgreSQL

1. Visit the official PostgreSQL download page:  
   👉 https://www.postgresql.org/download/windows/

2. Click on **"Download the installer"** by EDB.

3. Download the latest version suitable for your system.

---

## Step 2: Run the Installer

1. Run the downloaded `.exe` file.
2. Click **Next** through the setup screens.
3. Leave the default components selected:
   - PostgreSQL Server
   - pgAdmin
   - Stack Builder (optional)
4. Choose the installation directory or leave it default.

---

## Step 3: Set Superuser Password

- Set a strong password for the default PostgreSQL user: `postgres`.
- **IMPORTANT:** Save this password securely. You'll need it to access the database.

---

## Step 4: Choose Port Number

- Default is `5432`. You can leave it as is unless you're running multiple databases.

---

## Step 5: Set Locale and Install

1. Leave the locale to default or set according to your region.
2. Click **Next** and then **Install**.
3. Wait until installation is complete.

---

## Step 6: Add PostgreSQL to System PATH

1. Navigate to:

   ```
   C:\Program Files\PostgreSQL\<version>\bin
   ```

2. Copy the path.

3. Add it to your Windows **Environment Variables**:
   - Open Start → type **"Environment Variables"**
   - Click **Environment Variables...**
   - Under **System variables**, find `Path` → Click **Edit** → **New**
   - Paste the path, then click **OK**

---

## Step 7: Verify Installation

1. Open **Command Prompt** and run:

   ```bash
   psql -U postgres
   ```

2. Enter the password you set earlier.

3. If successful, you’ll see:

   ```
   postgres=#
   ```

4. Exit by typing:
   ```sql
   \q
   ```

---

## Optional: Fix Console Encoding Warning

If you see this warning:

```
WARNING: Console code page (850) differs from Windows code page (1252)
```

Run this before `psql`:

```bash
chcp 1252
```

---

## Stack Builder (Optional)

After installation, you may run **Stack Builder** to install:

- **PostGIS**: For geospatial support
- **pgAdmin plugins**: For extended GUI features
- **pgAgent**: For scheduling jobs
- **ODBC/JDBC Drivers**: For external application connectivity

> ⚠️ You **don’t need Stack Builder** for standard web development with PostgreSQL and Node.js.

---

## Use with Next.js and Prisma (Bonus)

Install Prisma:

```bash
npm install prisma @prisma/client
npx prisma init
```

Set your `.env`:

```env
DATABASE_URL="postgresql://postgres:<your-password>@localhost:5432/<your-db-name>"
```

Migrate your schema:

```bash
npx prisma migrate dev --name init
npx prisma generate
```

---

## You're Ready!

PostgreSQL is now installed and ready to use for local development.

---

## Resources

- Official docs: https://www.postgresql.org/docs/
- Prisma: https://www.prisma.io/docs
- Next.js: https://nextjs.org/docs

## Follow Me

[<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40'>](https://github.com/learnwithfair) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/facebook.svg' alt='facebook' height='40'>](https://www.facebook.com/learnwithfair/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg' alt='instagram' height='40'>](https://www.instagram.com/learnwithfair/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/twitter.svg' alt='twitter' height='40'>](https://www.twiter.com/learnwithfair/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/youtube.svg' alt='YouTube' height='40'>](https://www.youtube.com/@learnwithfair)

<!-- MARKDOWN LINKS & IMAGES -->

[youtube-shield]: https://img.shields.io/badge/-Youtube-black.svg?style=flat-square&logo=youtube&color=555&logoColor=white
[youtube-url]: https://youtube.com/@learnwithfair
[facebook-shield]: https://img.shields.io/badge/-Facebook-black.svg?style=flat-square&logo=facebook&color=555&logoColor=white
[facebook-url]: https://facebook.com/learnwithfair
[instagram-shield]: https://img.shields.io/badge/-Instagram-black.svg?style=flat-square&logo=instagram&color=555&logoColor=white
[instagram-url]: https://instagram.com/learnwithfair
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/rahatul-rabbi/
