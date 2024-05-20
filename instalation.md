# Instalation

## Requirements
- Make sure you have installed `docker` and `docker compose` in your machine.

## Steps
1. Clone this repository
```bash
git clone https://github.com/oaizab/calcom-docker.git
```

2. Go to the project directory
```bash
cd calcom-docker
```

3. Prepare the environment
```bash
cp .env.example .env
```
- Edit the `.env` file and set the values for the environment variables.
> `CALCOM_LICENSE_KEY` is the licence key provided by Calcom. (optional)
>
> `NEXT_PUBLIC_WEBAPP_URL` is the URL of the webapp. (optional)
> 
> `NEXTAUTH_URL` is the location of the authentication server. It should be the same as `{NEXT_PUBLIC_WEBAPP_URL}/api/auth`. (optional)
> 
> `NEXTAUTH_SECRET` is a secret key used by the authentication server. (required)
> 
> `CALENDSO_ENCRYPTION_KEY` is a secret key used by the calendar server. (required)
> 
> `DATABASE_URL` is the URL of the database. (required)
> 
> `DATABASE_DIRECT_URL` is the URL of the database used by the direct connection. (optional)

4. Pre-pull the images
```bash
docker compose pull
```

5. Start the services
```bash
docker compose up -d
```
- to start only the services needed for the webapp, make sure the database is running and run:
```bash
docker compose up -d calcom
```

6. Access the webapp at the URL you set in the `.env` file.

7. Setup admin user
  - Make sure the password is longer than 15 characters.
  - If you see a yellow warning, set the password again and longer.
  - After setting the password, you will be redirected to the login page.
  - If you don't see the admin settings set up 2fa and then you will see the admin settings.