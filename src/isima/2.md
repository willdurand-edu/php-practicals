Hotspot Map
===========

The Pitch
---------

As developers, we often need to find a place where we can hack, most of the time
because we are travelling, but also because we don't always have an office. A
nice place to hack has, at least, an internet connection (Wi-Fi) that is free of
charges. It is even better if there is some coffee available (free or not), and
plugs.

For instance, starbucks is pretty neat. They have great coffee, free Wi-Fi,
plugs, and sofa. That is what I would write as a description of such a place.
Some companies/startups provide a free desk for nomad people too. They provide
an Internet connection, and coffee for free. They can meet new people, and
sometimes it can be profitable.

Places have an address, and/or coordinates so that they can be displayed on a
map. It would be nice if the application could display the registered places on
a map. In other words, places are geolocated.

Talking about how places are displayed, it should be possible to filter places
by criteria (whether the Internet connection is free, number of results, how
far the place is, etc). For instance, one could type his own address, and ask
for the ten nearest places (_Hint:_ this require some mathematics formula).

Also, hackers often work late. In order to not being thrown away, each place
should have a sort of agenda, with open/closed periods. This is really
important!

Hackers use Twitter, so the application should be Twitter-oriented. For
instance, one could add himself to the list of "people having worked in this
place" by using a simple twitter button. This can be useful for those who want
to meet people as it also provides a list of people who are often at a given
place. See [techup.ch](http://techup.ch/) for instance.

It would be nice to be able to leave comments for each place. It is up to you to
manage the comments into the application itself, or to rely on a third-party
service.

Last but not the least, anyone can add a new place, but submissions are
moderated. Application's maintainers can either approve or reject a submission,
but also delete or update existing entries.

One more thing! Hackers gonna hack, so your application should act as a REST
API, meaning all features should be exposed through an API (submitting new
places, finding places, and so on).


Think!
------

According to Wikipedia (eurk), a **user story** _is one or more sentences in the
everyday or business language of the end user or user of a system that captures
what a user does or needs to do as part of his or her job function_. Most of the
time, we use the following pattern to represent a user story:

    "As a <role>, I want <goal/desire> so that <benefit>"

Based on the pitch above, find user stories that you will implement later on.
Prioritize your work.


What You Have To Do Now
-----------------------

Write an application that fits client's needs. You can use whatever tool you
want as far as you can explain your choices. You MUST write the application in
PHP. For instance, you can use [Slim](http://www.slimframework.com/), or
[Silex](http://silex.sensiolabs.org/) as framework. For geocoding stuff, you can
use the [Geocoder](http://geocoder-php.org/) library.

Rely on [Composer](https://getcomposer.org/) and
[Packagist](https://packagist.org) to install packages, and manage your
project's dependencies. You can ask for advices regarding the libraries you
would like to use.

Your code SHOULD be versioned. I don't mind if you loose your work before the
deadline.

You MUST use the Coding Standards as described in
[PSR-1](http://www.php-fig.org/psr/psr-1/) and
[PSR-2](http://www.php-fig.org/psr/psr-2/). The [PHP Coding Standards
Fixer](http://cs.sensiolabs.org/) could help you.

### The Model

**Important:** you MUST focus on the Model layer, and you MUST write this layer
yourself. No existing ORM allowed here. You MUST implement database design
patterns seen in class, but choose them carefully according to what you need to
do.

You can use a simple file as persistence storage, in YAML or JSON for instance.

If you want to use PDO, choose SQLite as database engine if you are running your
code on `etud`, otherwise feel free to use another database engine such as
PostgreSQL, or MySQL.

Then again, be sure to be able to explain your choices.

### REST API

You application MUST expose a REST API through the exact same methods in your
controllers. Use the appropriate HTTP verbs (methods), and status codes.

#### Content Negotiation

Content Negotiation is part of the HTTP protocol, used to serve a resource in
the best format for a client. You can read [RFC 2616:
HTTP/1.1](http://pretty-rfc.herokuapp.com/RFC2616) and [RFC 2295: content
negotiation](http://pretty-rfc.herokuapp.com/RFC2295) if you want more
information.

Content negotiation means that a single resource can be presented in different
ways, depending on the client preferences. To achieve this goal, **HTTP
headers** (`Accept`, `Accept-*`) are used by a client to tell the server about
its preferences.

Your application SHOULD be able to serve resources in:

* `HTML` using a template;
* `JSON` encoded data.

[Negotiation](https://github.com/willdurand/negotiation) can help you get the
best format from headers by handling content negotiation. The `Accept` header
**could** be found in `$_SERVER['HTTP_ACCEPT']`.

Your implementation SHOULD accept parameters encoded in:

* `application/x-www-form-urlencoded` - used when you submit a HTML form;
* `application/json`.

When a request has a body, it should provide a `Content-Type`. This content
type header is available in either `$_SERVER['HTTP_CONTENT_TYPE']` **or**
`$_SERVER['CONTENT_TYPE']`.

#### Serialization

HTML rendering is achieved through your template engine. Rendering your data in
other formats is called _serialization_. Serialization is the process of
converting a data structure or object state into a format that can be stored.

The serialization is handled by a Serializer. This serializer can be as simple
as the `json_encode()` function or you can use the [Serializer
Component](http://symfony.com/doc/current/components/serializer.html).

### Testing

Software testing is a **requirement** for all developers. Your job is **not** to
write code, it is all about providing solutions for given problems. The right
solution is always the one that works.

The question is: how do you ensure that your solution works? You cannot rely on
the well-known _it works on my machine™_. This is just silly. What you need to
do is to provide a set of automated tests.

Tests are more than just _assertions_ on some properties of your application,
it is also the best documentation you can provide to your customers/users because
tests are always up to date.

So, your application MUST be tested. Write unit tests, but also functional
tests. [Behat](http://docs.behat.org/) can help you with your functional tests.
It takes sort of user stories as input ;-)

Don't expect to have more than _10/20_ if you don't provide tests!

### Presentation Layer

While it is not the goal of this project, things that look nice are always
better than ugly things, even if those things don't work. In oher words, don't
neglect the presentation/design.


Important
---------

Le projet est à rendre par mail le **16 mars 2014** dernier délai. La pénalité
de retard se comptera à la minute près !

Les formats acceptés sont :

* une archive (`tar`, `tgz` ou `zip`) ;
* **ou** un dépôt distant (`git`, `svn`, etc.).

Le projet doit être accompagné d'instructions de mise en route. Ainsi que d'un
bilan rapide de ce qui a été fait/pas fait. Le format pour ce fichier doit être
**textuel**, donc `txt` ou `markdown`. Je ne peux pas ouvrir les fichiers Word
ou Open Office.

Ce bilan n'est pas un compte rendu formel, vous pouvez simplement énumérer ce
qui a été fait et ce qui n'a pas été fait, en faisant des phrases courtes. Il
devrait tenir sur une page, et c'est un fichier **obligatoire**.

Aucun retard ou problème technique ne sera toléré, c'est pourquoi il est
fortement conseillé de mettre également à disposition un lien de téléchargement
direct sur un service en ligne (dropbox, ubuntu one, google drive, etc.).

Si votre archive est corrompue, vous serez défaillant, faites en sorte d'envoyer
quelque chose de correct. Nous vérifierons ce point à chaque réception d'un
projet. Si votre archive est corrompue, nous vous l'indiquerons et vous aurez
avant 23h59 pour renvoyer une archive valide.

Vous devez nommer l'archive comme suit : `projet_<nom 1>_<nom 2>.zip`. Le mail
doit comporter la mention `[ZZ3F2 PHP]` dans le sujet du mail.
