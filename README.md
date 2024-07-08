### 1. Login.php
### 2. Home.php
### 3. NewPostForm.php

-----------------------------------

### Login.php (VISTA) 

#### Solicitud d'autenticació
POST [usuari, passowrd] => 'http://localhost/blog/Includes/login.php

#### Resposta servidor 
GET 'error'

*Accés a les dades*
```php
$_GET['error'];
```

### Home.php (VISTA)

#### Solicitud de vista de creació de post (BOTÓ AL FORMULARI)
GET => 'http://localhost/blog/Includes/new-post.php

#### Solicitud de logout (BOTÓ)
GET => 'http://localhost/blog/Includes/logout.php'

#### Resposta servidor
SESSION 'posts'

*Estructura de les dades*
```php
$posts = [
    id1 => [
        titol => 'asdasd',
        descripcio => 'asdadas',
        img_url => 'adada',
        data => 'adasd'
    ], 
    id2 => [
        titol => 'asdasd',
        descripcio => 'asdadas',
        img_url => 'adada',
        data => 'adasd'
    ],
]
```

*Accés a les dades*
```php
$_SESSION['posts'];
```

*Exemple de codi per a la vista*
```php
<ul>
    <?php foreach($_SESSION['posts'] as $post)> ?>
        <div>
            <img src= <?= $post->img_url ?>></img>
            <span><?= $post->titol ?></span>
            <p><?= $post->descripcio ?></p>
            <span><? $post->data ?></span>
        </div>
    <?php endforach ?>
</ul>
```

### NewPostForm.php (VISTA)

#### Solicitud de creació de post
POST [titol, descripcio, imatge] => 'http://localhost/blog/Includes/create-post.php'

#### Resposta servidor 
GET 'error'

*Accés a les dades*
```php
$_GET['error'];
```

```php
<span> <?= $_GET['error'] ?> </span>
````