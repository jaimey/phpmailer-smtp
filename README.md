#Library PHPMailer SMTP
This is a lightweight SMTP PHPMailer.
Simple, powerful and easy to use.

```php
date_default_timezone_set('America/Bogota');

require 'class.phpmailer.php';
require 'class.smtp.php';

$mail = new PHPMailer;
$mail->isSMTP();
$mail->SMTPDebug = 2;
$mail->Debugoutput = 'html';
$mail->Host       = 'smtp1.example.com';
$mail->Port = 465;
$mail->SMTPAuth = true;
$mail->Username = "user@example.com";
$mail->Password = "secret";
$mail->setFrom('from@example.com', 'Mailer');
$mail->addReplyTo('info@example.com', 'Information');
$mail->addAddress('to@gmail.com', 'Destination');
$mail->Subject = 'PHPMailer SMTP test';
$mail->Body= "Esto es una prueba";
$mail->AltBody = 'This is a plain-text message body';

if (!$mail->send()) {
    echo "Mailer Error: " . $mail->ErrorInfo;
} else {
    echo "Message sent!";
}
```