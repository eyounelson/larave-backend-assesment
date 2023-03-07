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


two ways to Refactor code

1.
```php
   function runOperations()
        {
            $error = null;

            if (!SUCCEEDED(Operation1())) {
               $error = OPERATION1FAILED;
            }
            if (!SUCCEEDED(Operation2())) {
               $error = OPERATION2FAILED;
            }
            if (!SUCCEEDED(Operation3())) {
               $error = OPERATION3FAILED;
            }
             if (!SUCCEEDED(Operation4())) {
             $error = OPERATION4FAILED;
            }
            
            return $error;
        }
```


2.
```php
   function runOperations()
        {
            $error = null;

          
            switch ($error) {
               case !SUCCEEDED(Operation1()):
                  echo $error = OPERATION1FAILED;;
                  break;
               case !SUCCEEDED(Operation2()):
                  echo $error = OPERATION2FAILED;;
                  break;
               case !SUCCEEDED(Operation3()):
                  echo $error = OPERATION3FAILED;
                  break;
               case !SUCCEEDED(Operation4()):
                  echo $error = OPERATION4FAILED;
                  break;
               default:
                  echo return $error;
                  break;
            }
            
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
