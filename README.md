# GooglePlus

## Installation

``` bash
gem install google_plus
```

## Methods

``` ruby
GooglePlus.has_api? # true

GooglePlus.api_key = '123'

# get a person
person = GooglePlus::Person.get(123)
person.display_name

# get their activities (returns a cursor)
cursor = person.activities_list
while cursor.next_page
  cursor.items.count # a bunch of activities
end

# or an activity by id
actvitiy = GooglePlus::Activity.get(123)
activity.person

# you can pass params into the cursor
cursor = person.activities_list(:user_ip => '...', :max_results => 5)

# you can pass params into a next page
cursor.items(:max_results => 2) # OR
cursor.next_page(:max_results => 2)
```

## Dependencies

* rest_client

## License

(The MIT License)

Copyright © 2011 John Crepezzi

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the ‘Software’), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED ‘AS IS’, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE. 
