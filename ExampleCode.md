# Introduction #

Some example code...


# Details #

```
<?php

    // Create permissions...        
    $perms = new FacebookPermissions;

    // Get facebook api instance
    $api = FacebookApi::getInstance($perms);

    // print out the current user data... :)
    print_r($api->user); 


    // Ok, now post on the wall

    $f = new FacebookPost;
    $f->message  = "Test message";
    $f->caption = "Test caption";
    $f->description = "Test description";
    $f->name = 'test';
    $f->link = "http://google.com";
    $f->actions[] = array("name"=> "View on Google", "link"=> "http://www.google.com");
    
    // $f->to = "Any fb id"; // Also You can send this post to the wall of the friends, if you want

    // Publish the new post on the wall
    $f->publish();
    
    echo $f->id;    // The id of the new post

    // Create new event...

    $event = new FacebookEvent; // create empty event
    $event->name="Test";        // Name
    $event->start_time = date("Y-m-20"); // Start
    $event->end_time = date("Y-m-25");  // End 
    $event->description = "Description of the event";   //Descr
    $event->publish();      // Publish event
    
    // print out the friends
    print_r($f->friends);

    // print out the albums
    print_r($f->albums);
 
    // print out photos in the first album
    print_r($f->albums[0]->photos);   

    // print comments of the first photo in the first album
    print_r($f->albums[0]->photos[0]->comments);   

    // print likes of the first photo in the first album
    print_r($f->albums[0]->photos[0]->likes);   

  
?>
```