**Start Project**

```bash
django-admin startproject wang_xiuyuan_final_project
```

**Run Server**

```bash
python manage.py runserver 8000
```

**Create Database**

```bash
python manage.py migrate
```

**Create Superuser**

```bash
python manage.py createsuperuser
```

**Create App**

```bash
python manage.py startapp shopinfo
```

**Change `settings.py`**

- add `'shopinfo'` to `INSTALLED_APPS`

**Define Models**

- go to `models.py`
- define each model class

**Make Migrations**

```bash
python manage.py makemigrations shopinfo
```

**Migrate Database**

```bash
python manage.py migrate shopinfo
```

- Note: refresh to reload database tables

**Register App**

- go to `admin.py`
- register each model class

