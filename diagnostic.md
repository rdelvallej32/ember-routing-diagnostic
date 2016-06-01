# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The router maps a url to a route. The main tasks in an Ember route: (1) to parse the URL for a given route, and (2) to use information from that URL to load model data.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to "campus.boston" }}{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first is a nested route and the second is not a nested route The first renders a product template
    within the products template versus just rendering a product template.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md

    ```js
    export default Ember.Route.extend({
    model: function(params){
    return [
      {
        id: 123,
        name: 'movie one',
      },

      {
        id: 124,
        name: 'movie one',
      },
      ][params.product_id - 1];
      }
    });

    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    ```html

      <ul>
      {{#each model as |movie| }}
        <li>{{movie}}</li>
        {{/each}}
      </ul>


    ```
