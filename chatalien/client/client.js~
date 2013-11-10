Template.messages.messages = function() {
			return Messages.find({},{sort:{time:-1}});
}

Template.input.events = {
	'keydown input#message': function(event) {

		if (Meteor.user()) { /*COMO PONERLO FUERA Y QUE SE ACTUALICE?*/
			var name = Meteor.user().emails[0].address;
		} else {
			var name = 'Anonymous';
		}

		if(event.which == 13) {
			var message = $('#message');
			if (message.val()) {
				Messages.insert({
					name: name,
					message: message.val(),
					time: Date.now()
				});
			}
			message.val('');
		}
	}
}

Accounts.ui.config({
	passwordSignupFields: 'USERNAME_AND_OPTIOPNAL_EMAIL'
});
