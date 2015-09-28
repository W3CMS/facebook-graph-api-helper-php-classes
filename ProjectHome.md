See [example.php](http://code.google.com/p/facebook-graph-api-helper-php-classes/source/browse/trunk/example.php) for the newest example code.

---

What's new?

---

Now using the newest (v3) PHP SDK.

Photo uploading support

Same bugfixes


---

Some php classes to request and post information to facebook.
You can:
  * Read user data ( name, email, birthday, location, etc.)
  * List friends
  * Read friends data
  * List albums
  * Create album
  * Upload photo
  * Manage post ( publish post, delete post, like post )
  * Manage likes
  * Manage pages
  * Publish as page
  * Like as page
  * Manage events ( create event, delete event )
  * and so more...

Fell free to contact me, if you have any question or idea.

Same example code:

The simple way to facebook is:

```
<?php

    // Create permissions...        
    $perms = new FacebookPermissions; // Don't need, only if you want request more permission than the basic settings.
    // Get facebook api instance
    $api = FacebookApi::getInstance($perms);  // Or: $api = FacebookApi::getInstance() also works fine

    // print out the current user first name... :) Try print_r($api->user); ! ;-)
    echo $api->user->first_name;


    // Ok, now post on the wall

    $f = new FacebookPost;
    $f->message  = "Test message";
    $f->caption = "Test caption";
    $f->description = "Test description";
    $f->name = 'test';
    $f->link = "http://google.com";
    $f->actions[] = array("name"=> "View on Google", "link"=> "http://www.google.com");

    // Publish the new post on the wall
    $f->publish();
    
    echo $f->id;    // The id of the new post


    // Create new event...

    $event = new FacebookEvent; // create new event
    $event->name="Test";        // Name
    $event->start_time = "2012-12-12"; // Start date
    $event->end_time = "2012-12-25";  // End date
    $event->description = "Description of the event";   //Description
    $event->publish();      // Publish event

?>
```

It's really simple...