# Amazon AWS for Kohana 3+

A module for managing amazon aws [Kohana framework](http://kohanaframework.org/) (v3.0+).

## Quick Start

This module is wrapper for configure aws sdk.

### Modify the Config File

Move config/amazon.php to your application config directory and modify your Amazon security information as Amazon indicates.

### Example:

    class Controller_Amazon extends Controller {
        
        public function action_s3()
        {
            $s3 = new AmazonS3();
            $bucket = 'my-bucket' . strtolower($s3->key);
 
            $response = $s3->get_object($bucket, 'prefix with spaces/aeiou/aeiou/aeiou with spaces.txt');
             
            // Success?
            var_dump($response->isOK());
        }
		
        public function action_sqs()
        {
          $sqs = new AmazonSQS();
          
          $response = $sqs->list_queues();
 
          // Success?
          var_dump($response->isOK());
        }
        
    }
    
### Docs

See AWS SDK for php Documentation (http://docs.amazonwebservices.com/AWSSDKforPHP/latest)