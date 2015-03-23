# Volt-Card

### Note that this is a WIP but I am easily contacted, love PR's, and just wanna give people cool things.

[Card](http://www.github.com/jessepollak/card) is a wonderful library that makes credit card forms easy and beautiful with a single
line of code.
![card](http://i.imgur.com/qG3TenO.gifv)

## Installation

Add this line to your application's Gemfile:

    gem 'volt-card'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install volt-card

Proceed to add it to `dependencies.rb`

```RUBY
component 'card'
```

## Usage

Inside any form like this...

```RUBY
<div class="demo-container">
  <div class="card-wrapper"></div>
    <div class="form-container active">
      <form e-submit="process_payment">
        <input placeholder="Card number" type="text" name="number" value="{{ _card_number }}" >
        <input placeholder="Full name" type="text" name="name"value="{{ _full_name }}" >
        <input placeholder="MM/YY" type="text" name="expiry"value="{{ _exp_date }}">
        <input placeholder="CVC" type="text" name="cvc"value="{{ _cvc }}">
      </form>
    </div>
  </div>
</div>
```

we go on to add:

```
# form is up here
...
{{ card = `new Card({form: document.querySelector('form'),container: '.card-wrapper'});` }}
{{ # Note that currently only inline JS via tickmarks is supported (` notation for Opal) }}
...
```

And wa-la, CSS is included for all major carriers, and it also has built in validations. Send
it serverside and we have added a single line and made our form beautiful, and added a great element
to the general UX of our site.

Props to [@jessepollak](http://www.twitter.com/jessepollak) for building Card originally. I am but a guy porting it.

1. Fork it ( http://github.com/[my-github-username]/volt-card/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
