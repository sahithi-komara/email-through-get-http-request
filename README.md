# email-through-get-http-request
HTTP Request is a messege from the client to the server

If user clicks on the below hyperlink read recent email

The HTTP request messege will be sent as: GET/categories/02/gmail HTTP/1.1 Host localhost:2400 User Agent: Monila/4.0 (compatible Windows NT) URL-/categories/02/gmail Request Method - GET HTTP Specification - 1.1 Domain: localhost, Port: 2400

programme:

def send_message(service, user_id, message): """Send an email message.

Args: service: Authorized Gmail API service instance. user_id: User's email address. The special value "me" can be used to indicate the authenticated user. message: Message to be sent.

Returns: Sent Message. """ try: message = (service.users().messages().send(userId=user_id, body=message) .execute()) print 'Message Id: %s' % message['id'] return message except errors.HttpError, error: print 'An error occurred: %s' % error
