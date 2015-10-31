# JsAndValidators
General functions abuout javascript, jquery, etc, that has been done while the work and we couldn't remember

# Example about how add an method to the API
This example is for add a type float_comma  using a var like 123456789,123456789 but this change the point by comma
´´´
jQuery.validator.addMethod("float_comma", function(value, element) {
	            flotantes = /^[0-9]+,+[0-9]+$/;
	            numeros = /^[0-9]+$/;
	            if(value.match(numeros) || value.match(flotantes)){
	                return true;
	            }
	            return false;
	        }, "Value should be numeric");
´´´
