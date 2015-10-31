# JsAndValidators
General functions abuout javascript, jquery, etc, that has been done while the work and we couldn't remember

# Example about how add an method to the API
This example is for add a type float_comma  using a var like 123456789,123456789 but this change the point by comma
but when you will to recive in the contreller, you have to make a function for change the comma by a point again,
on the contrary you'll have an error with the data type.

	jQuery.validator.addMethod("float_comma", function(value, element) {
	            flotantes = /^[0-9]+,+[0-9]+$/;
	            numeros = /^[0-9]+$/;
	            if(value.match(numeros) || value.match(flotantes)){
	                return true;
	            }
	            return false;
	        }, "Value should be numeric");

