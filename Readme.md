## Kill The if/else
How would you refactor this code to remove the multi-level nested ifs

```php
   function runOperations()
        {
            $$error = null;

            if (SUCCEEDED(Operation1())) {
                if (SUCCEEDED(Operation2())) {
                    if (SUCCEEDED(Operation3())) {
                        if (SUCCEEDED(Operation4())) {
                        } else {
                            $error = OPERATION4FAILED;
                        }
                    } else {
                        $error = OPERATION3FAILED;
                    }
                } else {
                    $error = OPERATION2FAILED;
                }
            } else {
                $error = OPERATION1FAILED;
            }

            return $error;
        }
```


## Two
The world as we know it has fallen into an apocalyptic scenario. A laboratory-made virus is transforming human beings and animals into zombies, hungry for fresh flesh.

You, as a zombie resistance member (and the last survivor who knows how to code), was designated to develop a system to share the location of infected humans, so others can avoid such.

Using the laravel framework, write a simple api that:

- lists all infected humans
- has an endpoint/interface to flag oe as cured/disinfected. Then such person will no longer show up in the list above.
- update the location of any infected human

### Notes
- send response using [laravel responder](https://github.com/flugg/laravel-responder)
- Write concise and clear commit messages, splitting your changes in little pieces.
- Add a some form of automated tests - with phpunit
- Write concise and clear commit messages, splitting your changes in little pieces.
- As much as possible, keep your code the 'Laravel way'