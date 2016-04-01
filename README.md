# Integration

These are some instructions on how to prepare the html which will make integration a lot easier.

If any of this is impractical for you, or beyond what you would normally do, don't worry. But anything you can do will make the process a bit smoother.

Likewise, any questions, feel free to ask :)

## Index

1. Each image should be a static_url tag followed by the image name, no path needed e.g. ```src="{{ STATIC_URL }}houses-icon.png"```

2. The index page should have a block that the partials are injected into.
This is simply

	```{% block quote %}{% endblock %}```
		
In the index page it will look like:

```
  <div class="Section one">
      <div class="row">
        <div class="small-12 medium-8 columns box booking-form">
          {% block quote %}{% endblock %}
        </div>
        <div class="small-12 medium-4 columns box">
          <p class="title">Which survey is right for me?</p>
          <img class="sml" src="{{ STATIC_URL }}houses-icon.png">
          <p>Do you want to know about the property's condition or value?</p>
          <button>Condition Only</button>
          <button>Value Only</button>
          <button>Both</button>
          <p class="lastP">Still unsure? Click here to compare the contents of each type of survey</p>
        </div>
      </div>
  </div>
  ```
  
## Partials

Example partial:

```
{% extends "quote/quote.html" %}
{% block quote_content %}
    <img src="{{ STATIC_URL }}houses-icon.png">
    <h2>Please give us the estate agent or vendor details</h2>
    <form action="" method="post" class="booking-contact-form">{% csrf_token %}
        <div class="booking-contact-col">
            <ul class="booking-contact">
                <li><input type="text" name="" placeholder="Name"></li>
                <li><input type="tel" name="" placeholder="Phone Number"></li>
                <li><input type="email" name="" placeholder="Email"></li>
            </ul>
        </div>
        <input class="btn addresses-btn" type="submit" value="Continue">
    </form>
{% endblock %}
```

1. Each partial begins with an extend tag e.g. ```{% extends "quote/quote.html" %}```

2. Each partial should be wrapped in a block. e.g. ```{% block quote_content %} partial {% endblock %} ```

3. A csrf_token should be included after each form opening tag: ```<form>{% csrf_token %}```

4. Each image should be a static_url tag followed by the image name, no path needed e.g. ```{{ STATIC_URL }}houses-icon.png```

5. Keep each input name and form action blank.






