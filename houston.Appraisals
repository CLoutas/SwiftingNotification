##
# HOUSTON
# ---------
#
# Houston is a simple gem for sending Apple Push Notifications. Pass your credentials, construct your message, and send it.
# https://github.com/nomad/houston
##

require 'houston'

# Environment variables are automatically read, or can be overridden by any specified options. You can also
# conveniently use `Houston::Client.development` or `Houston::Client.production`.
APN = Houston::Client.development
APN.certificate = File.read("/Users/gurth4ng/Downloads/Certificates.pem")

# An example of the token sent back when a device registers for notifications
token = "<fc5c5f8b8a151d30acc06a5946786580e15edb349fc44f2f0c9eb4cecb98e9f9>"

# Create a notification that alerts a message to the user, plays a sound, and sets the badge on the app
notification = Houston::Notification.new(device: token)
notification.alert = {
			title: "SampleTitle",
			body: "SampleBody"
		}

# Notifications can also change the badge count, have a custom sound, have a category identifier, indicate available Newsstand content, or pass along arbitrary data.
notification.badge = 57
notification.sound = "sosumi.aiff"
notification.category = "INVITE_CATEGORY"
# notification.content_available = true
notification.mutable_content = true
notification.custom_data = { foo: "bar" }

# And... sent! That's all it takes.
APN.push(notification)
