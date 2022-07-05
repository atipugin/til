# Use I18n with custom lambda functions

Sometimes you need to add some logic to your localized strings. For example, you
need a time format that returns "Today" for today's date or "Jan 01" for any
other day. You can use `.rb` file format (not `.yml`) for locale files and
return lambdas as values:

```ruby
# config/locales/en.rb
{
  en: {
    time: {
      formats: {
        today_or_not: ->(time) { time.today? ? 'Today' : '%b %d' }
      }
    }
  }
}
```

Result:

```ruby
I18n.l(Time.zone.now, format: :today_or_not)
# => "Today"

I18n.l(Time.zone.now.beginning_of_year, format: :today_or_not)
# => "Jan 01"
```
