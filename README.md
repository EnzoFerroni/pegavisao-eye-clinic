# PegaVisão

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python&logoColor=white)](https://www.python.org)
[![Django](https://img.shields.io/badge/Django-4.2-092E20?logo=django&logoColor=white)](https://www.djangoproject.com)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?logo=bootstrap&logoColor=white)](https://getbootstrap.com)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A Django web app for an eye clinic: browse specialties and let patients book, edit and cancel appointments.

## Table of Contents

- [About](#about)
- [Features](#features)
- [Built With](#built-with)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [License](#license)

## About

PegaVisão is a web development project from Universidade Presbiteriana Mackenzie
(2024). It models the website of an ophthalmology clinic, with a public area listing
the clinic's services and a logged-in area where patients manage their appointments.
The UI is in Portuguese. This is an academic project and is not affiliated with any
real clinic.

## Features

- Home, about and service pages for ten specialties (cataract, glaucoma, keratoconus, refractive surgery and more)
- Service catalog managed in the Django admin, with images and availability
- User sign-up, login and logout
- Book an appointment choosing the specialty, the doctor and the date
- List, edit and cancel booked appointments

## Built With

- Django 4.2 with two apps: `PV` (clinic) and `Usuarios` (accounts)
- SQLite for local development
- Bootstrap 5 via `django-bootstrap-v5`
- Docker image for deployment

## Getting Started

Requirements: Python 3.10.

```bash
git clone https://github.com/EnzoFerroni/pegavisao-eye-clinic.git
cd pegavisao-eye-clinic
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate
pip install -r requirements.txt

export SECRET_KEY=any-long-random-string
python manage.py migrate
python manage.py createsuperuser  # to add services in /admin
python manage.py runserver
```

Open http://127.0.0.1:8000.

**With Docker**

```bash
docker build -t pegavisao .
docker run -p 8000:8000 -e SECRET_KEY=any-long-random-string pegavisao
```

## Project Structure

```
├── apps/
│   ├── PV/          Services and appointments (models, views, forms, urls)
│   └── Usuarios/    Sign-up and login
├── setup/           Django settings, URLs and static files
├── templates/       HTML templates (clinica, usuarios)
├── media/           Uploaded service images
└── Dockerfile
```

## License

Released under the [MIT License](LICENSE). Copyright (c) 2024 Enzo Ferroni. Clinic
photos and third-party logos belong to their respective owners.
