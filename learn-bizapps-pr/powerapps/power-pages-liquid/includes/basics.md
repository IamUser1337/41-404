Similar to any traditional programming language, Liquid has a defined syntax, can use variable definitions, and includes constructs such as output and logic. Liquid constructs are recognizable by two sets of delimiters: the double brace delimiters `{{ }}`, which denote output from the objects and variables, and the brace percentage delimiters `{% %}`, which denote logic and control flow.

> [!TIP]
> Page content and content snippets help make it easier for you to "practice" Liquid by entering the Liquid content in Power Pages design studio. As you're moving along in this learning content, try any sample Liquid fragments by copying and pasting the code directly into a page by using Power Pages design studio or Visual Studio Code.

## Output

An output statement is a set of double braces that contain an expression. When the output is rendered, it's replaced with the value of that expression. The expression can include Liquid objects, their properties, and variables. The following example shows a simple output statement:

```twig
Hello {{ user.firstname }} from {{ 'Power Pages' }}
```

Assuming that the user's first name is Doug, this output statement produces the following result:

> Hello Doug from Power Pages

## Filters

Output markup can take filters, which modify the result of the output statement. You can add filters by following the output expression with a pipe character (`|`), the name of the filter, and optional parameters after a colon (`:`).

```twig
Hello {{ user.firstname | upcase }} from {{ 'Power Pages' }}. The date is {{ 'now' | date: 'MMMM d yyyy' }}
```

This filter statement generates the following result:

> Hello DOUG from Power Pages. The date is May 25, 2023.

## Tags

You can use tags for the logic and control flow in your template, for example (HTML has been added to the example as well):

```twig
{% assign product = 'Power Pages' %}

<p>
    {% if user %}
        Hello, {{ user.firstname | upcase }}, from <strong>{{ product }}</strong>.
    {% else %}
        Greetings, <em>visitor</em>, from <strong>{{ product }}</strong>!
    {% endif %}
</p>

<p>The time is {{ 'now' | date: 'g' }}</p>
```

In this fragment, the `assign` tag creates a new variable, and the `if... else` construct generates output that depends on whether the user has been defined or not (in other words, whether a website visitor has signed in). The output for an anonymous user is as follows:

> Greetings, *visitor*, from **Power Pages**!
>
> The time is 5/24/2023 11:33 AM

Liquid includes several built-in objects and tags that make it versatile and flexible. The real benefits come from the Liquid extensions that are implemented by Power Pages.
