## Introduction

Royalcms-Metable is a package for easily attaching arbitrary data to Eloquent models for Royalcms 5.

Features

One-to-many polymorphic relationship allows attaching data to Eloquent models without needing to adjust the database schema.
Type conversion system allows data of numerous different scalar and object types to be stored, queried and retrieved. See the list of supported :ref:`datatypes`.

## Example Usage

Attach some metadata to an eloquent model

```php
<?php
$post = Post::create($this->request->input());
$post->setMeta('color', 'blue');
```

Query the model by its metadata

```php
<?php
$post = Post::whereMeta('color', 'blue');
```

Retrieve the metadata from a model

```php
<?php
$value = $post->getMeta('color');
```

## Documents

- [Handling Meta](handling_meta)
- [Querying Meta](querying_meta)
- [Data Types](datatypes)