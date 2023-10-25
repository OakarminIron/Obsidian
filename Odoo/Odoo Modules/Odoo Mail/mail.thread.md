[[mail.channel]]
[[mail.message]]
[[mail.follower]]
mail_thread model is meant to be inherited by any model that needs to act as a discussion topic on which messages can be attached. Public methods are prefixed with ``message_`` in order to avoid name collisions with methods of the models that will inherit from this class.