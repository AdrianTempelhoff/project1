Specl
--------------------------------------------------------------------------------

Extend CSS, on the fly.

**NOTE:**
That shall be note


Usage
--------------------------------------------------------------------------------

Coming Soon!

For now, take a look at `example/index.html`


To Do
--------------------------------------------------------------------------------

  * @rules for specification:

        @specify {
          @filter('innermost') {
            $(this.element).find('*').size() === 0;
          }

          @property('-local-important') {
            $(this.element).css({ border: this.args[0] + ' solid ' + this.args[1] });
          }

          @property('-local-iconic', Specl.handler);
        }

  * inline handlers:
  
        -spec-filter : 'innermost' $(this.element).find('*').size() === 0;
        -spec-property : '-local-important' $(this.element).css({ border: this.args[0] + ' solid ' + this.args[1] });
  
  * determine if I should be storing property "applications". like:

        for(var selector in css) {
          for(var property in css[selector]) {
            if(/^-local/.test(property)) {
              if( ! property_applications[property]) {
                property_applications[property] = [];
              }
              property_applications[property].push({ selector: selector, args: css[selector][property].split(' ') });
            }
          }
        }
  
  * usage(?):

        $().ready(function(){
          Specl.transform('link[type=text/css]');
          Specl.specify(function() {
            this.filter('innermost', function() {
              return $(this.element).find('*').size() === 0;
            });
          });

          specl = new Specl();
          specl.transform('link[type=text/css]');
          specl.transform('style');
          specl.specify(function() {
            this.filter('innermost', function() {
              return $(this.element).find('*').size() === 0;
            });
          });
        })


References/Credits
--------------------------------------------------------------------------------

  * http://us.com/
