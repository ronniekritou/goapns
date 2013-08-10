go-apns
=======

Apple Notification Service API written in GoLang (forked from github.com/Mistobaan/go-apns)


# Install

        go get github.com/akhenakh/goapns

# Usage
		client = apns.NewClient(apns.APPLE_PUSH_SANDBOX, "apns-dev-cert.pem", "apns-dev-key-noenc.pem")

		alert := apns.PayloadAlert{
			LocArgs:      msg.Params,
			ActionLocKey: "PLAY",
			LocKey = "FOUND_W"
		}
		payloadNotif := apns.PayloadNotification{Alert: alert}

		payload := apns.PayloadGame{Aps: payloadNotif}

		payloadJSON, err := json.Marshal(payload)

		client.SendPayloadString()

		feedback = apns.NewFeedbackClient(apns.APPLE_FEEDBACK_SANDBOX, "apns-dev-cert.pem", "apns-dev-key-noenc.pem")
		feedback.StartListening() listen for channel


# Customized notif
		type ApnsPayloadGame struct {
			Aps    PayloadNotification `json:"aps"`
			GameId string                  `json:"game_id"`
		}