---
layout: page
title: "JavaScript localeconv function"
comments: true
sharing: true
footer: true
alias:
- /functions/view/localeconv:782
- /functions/view/localeconv
- /functions/view/782
- /functions/localeconv:782
- /functions/782
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's localeconv

{% codeblock strings/localeconv.js lang:js https://raw.github.com/kvz/phpjs/master/functions/strings/localeconv.js raw on github %}
function localeconv() {
  //  discuss at: http://phpjs.org/functions/localeconv/
  // original by: Brett Zamir (http://brett-zamir.me)
  //  depends on: setlocale
  //   example 1: setlocale('LC_ALL', 'en_US');
  //   example 1: localeconv();
  //   returns 1: {decimal_point: '.', thousands_sep: '', positive_sign: '', negative_sign: '-', int_frac_digits: 2, frac_digits: 2, p_cs_precedes: 1, p_sep_by_space: 0, n_cs_precedes: 1, n_sep_by_space: 0, p_sign_posn: 1, n_sign_posn: 1, grouping: [], int_curr_symbol: 'USD ', currency_symbol: '$', mon_decimal_point: '.', mon_thousands_sep: ',', mon_grouping: [3, 3]}

  var arr = {},
    prop = '';

  // BEGIN REDUNDANT
  this.setlocale('LC_ALL', 0); // ensure setup of localization variables takes place, if not already
  // END REDUNDANT
  // Make copies
  for (prop in this.php_js.locales[this.php_js.localeCategories.LC_NUMERIC].LC_NUMERIC) {
    arr[prop] = this.php_js.locales[this.php_js.localeCategories.LC_NUMERIC].LC_NUMERIC[prop];
  }
  for (prop in this.php_js.locales[this.php_js.localeCategories.LC_MONETARY].LC_MONETARY) {
    arr[prop] = this.php_js.locales[this.php_js.localeCategories.LC_MONETARY].LC_MONETARY[prop];
  }

  return arr;
}
{% endcodeblock %}

 - [Raw function on GitHub](https://github.com/kvz/phpjs/blob/master/functions/strings/localeconv.js)

Please note that php.js uses JavaScript objects as substitutes for PHP arrays, they are 
the closest match to this hashtable-like data structure. 

Please also note that php.js offers community built functions and goes by the 
[McDonald's Theory](https://medium.com/what-i-learned-building/9216e1c9da7d). We'll put online 
functions that are far from perfect, in the hopes to spark better contributions. 
Do you have one? Then please just: 

 - [Edit on GitHub](https://github.com/kvz/phpjs/edit/master/functions/strings/localeconv.js)


### Other PHP functions in the strings extension
{% render_partial _includes/custom/strings.html %}
