yii2-curl extension
===================
Curl Wrapper for Yii framework v2.0
Update

This can now be used for non-Yii applications as well. (still works as a component if you're using Yii)
Lazy initialization of curl.
+ getHeader method
Requirements

PHP 5.3+
Yii 1.1.7 (should work on older versions too)
Curl and php-curl installed
Setup instructions

Place Curl.php or git clone into protected/extensions/curl folder of your project
in main.php, or console.php add the following to 'components':
    'curl' => array(
        'class' => 'ext.curl.Curl',
        'options' => array(/* additional curl options */),
    ),
Usage

to GET a page with default params
    $output = Yii::app()->curl->get($url, $params);
    // output will contain the result of the query
    // $params - query that'll be appended to the url
to POST data to a page
    $output = Yii::app()->curl->post($url, $data);
    // $data - data that will be POSTed
to PUT data
    $output = Yii::app()->curl->put($url, $data, $params);
    // $data - data that will be sent in the body of the PUT
to PATCH data
    $output = Yii::app()->curl->patch($url, $data);
    // $data - data that will be PATCHed
to DELETE
    $output = Yii::app()->curl->delete($url, $params);
    // $params - query that'll be appended to the url
to set options before GET or POST
    $output = Yii::app()->curl->setOption($name, $value)->get($url, $params);
    // $name & $value - CURL options
    $output = Yii::app()->curl->setOptions(array($name => $value))->get($get, $params);
    // pass key value pairs containing the CURL options