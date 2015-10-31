# JsAndValidators
General functions abuout javascript, jquery, etc, that has been done while the work and we couldn't remember

# Example about how add a method to the API
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


# How make a validator about the float number that can't enter characters
This function also can add point for the thousand.
See an example in here: http://jsfiddle.net/leonelphm/1tx5qc3d/

javascript:

	function format(separador, period) {
	    var romper = this.toString().split(',');
	    var numeric = romper[0];
	    var decimal = romper.length > 1 ? period + romper[1] : '';
	    var reg = /(\d+)(\d{3})/;
	    while (reg.test(numeric)) {
	        numeric = numeric.replace(reg, '$1' + separador + '$2');
	        console.log(numeric)
	    }
	    return numeric + decimal;
	}
	$(document).ready(function(){
	    $('#myinput').on('keyup', function(){
	        this.value = (this.value + '').replace(/[^\d,]/g, '');
	        $(this).val(format.call($(this).val().split('.').join(''),'.',','));
	    });
	});
