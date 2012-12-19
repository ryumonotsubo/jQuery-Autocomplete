#Ajax AutoComplete for jQuery

Ajax Autocomplete for jQuery allows you to easily create 
autocomplete/autosuggest boxes for text input fields.


##Usage

Html:

    <input type="text" name="country" id="autocomplete"/>

Ajax lookup:

    $('#autocomplete').autocomplete({
        serviceUrl: '/autocomplete/countries',
        onSelect: function (suggestion) {
            alert('You selected: ' + suggestion.value + ', ' + suggestion.data);
        }
    });

Local lookup (no ajax):

    var countries = [
       { value: 'Andorra', data: 'AD' },
       // ...
       { value: 'Zimbabwe', data: 'ZZ' }
    ];

    $('#autocomplete').autocomplete({
        lookup: countries,
        onSelect: function (suggestion) {
            alert('You selected: ' + suggestion.value + ', ' + suggestion.data);
        }
    });

##Styling

Generated HTML markup for suggestions is displayed bellow. You may style it any way you'd like.

    <div class="autocomplete">
        <div class="autocomplete-suggestion autocomplete-selected">...</div>
        <div class="autocomplete-suggestion">...</div>
        <div class="autocomplete-suggestion">...</div>
    </div>

##Response Format

Response from the server must be JSON formatted following JavaScript object:

    {
        query: "Unit",
        suggestions: [
            { value: "United Arab Emirates", data: "AE" },
            { value: "United Kingdom",       data: "UK" },
            { value: "United States",        data: "US" }
        ]
    }

Data can be any value or object. Data object is passed to formatResults function and onSelect callback. Alternatively, if there is no data you can supply just a string array for suggestions:

    {
        query: "Unit",
        suggestions: ["United Arab Emirates", "United Kingdom", "United States"]
    }

Important: query value must match original value in the input field, otherwise suggestions will not be displayed.

##License

Ajax Autocomplete for jQuery is freely distributable under the 
terms of an MIT-style [license](https://github.com/devbridge/jQuery-Autocomplete/dist/license.txt).

Copyright notice and permission notice shall be included in all 
copies or substantial portions of the Software.

##Authors

Tomas Kirda / [@tkirda](https://twitter.com/tkirda)
