# Admonitions

Admonitions are a great way to include side content, without significantly interrupting the document flow. Sphinx provides several different types of admonitions and allows for the inclusion and nesting of arbitrary content.

## Basic Usage

````{furo-demo}
```{note} This is what the most basic admonitions look like.
```

```{note}
It is *possible* to have multiple paragraphs in the same admonition.

If you really want, you can even have lists, or code, or tables.
```

This is from Markdown.

+++

.. note:: This is what the most basic admonitions look like.


.. note::
   It is *possible* to have multiple paragraphs in the same admonition.

   If you really want, you can even have lists, or code, or tables.


This is from reStructuredText.
````

## Custom Titles

````{furo-demo}
```{admonition} Look ma! A custom title.
It looks different though.
```

```{admonition} Another Custom Title
:class: note

Maaa! I made it look the same by setting the class.
```

+++

.. admonition:: Look ma! A custom title.

   It looks different though.


.. admonition:: Another Custom Title
   :class: note

   Maaa! I made it look the same by setting the class.

````

## Supported types

### `admonition`

```{admonition} The one with the custom titles.
It's got a certain charm to it.
```

### `attention`

```{attention}
Climate change is real.
```

### `caution`

```{caution}
Cliff ahead: Don't drive off it.
```

### `danger`

```{danger}
Mad scientist at work!
```

### `error`

```{error}
Does not compute.
```

### `hint`

```{hint}
Insulators insulate, until they are subject to ______ voltage.
```

### `important`

```{important}
Tech is not neutral, nor is it apolitical.
```

### `note`

```{note}
This is a note.
```

### `seealso`

```{seealso}
Other relevant information.
```

### `tip`

```{tip}
25% if the service is good.
```

### `todo`

This needs the `sphinx.ext.todo` extension.

```{todo}
Figure out why this extension uses `admonition-todo` as the class, instead of using `todo` (like every other admonition style in Sphinx).
```

### `warning`

```{warning}
Reader discretion is strongly advised.
```

## Nesting admonitions

``````{furo-demo}
`````{note}
You can nest admonitions.

````{warning}
But you really should not.

```{danger}
It's distracting.
```

And can be confusing for the user to understand.
````

And, honestly, looks weird.
`````

+++

.. note::

   You can nest admonitions.

   .. warning::

      But you really should not.

      .. danger::

         It's distracting.

      And can be confusing for the user to understand.

   And, honestly, looks weird.

``````

## Custom Admonitions

It is possible to define custom admonitions for use with Furo. This is done by
[including custom CSS](../customisation/injecting.md) in the site.

The CSS would be something like:

```css
.admonition.pied-piper {
  background: rgba(43, 155, 70, 0.1);
  border-left: 4px solid rgb(43, 155, 70)
}
.admonition.pied-piper > p:first-child {
  color: rgb(43, 155, 70)
}
```

With this, you can now use this by setting the `:class: pied-piper` on an
admonition:

````{furo-demo}

```{admonition} Pied Piper
:class: pied-piper

This is neat, right?
```

This is from Markdown.

+++

.. admonition:: Pied Piper
   :class: pied-piper

   This is neat, right?


This is from reStructuredText.

````
