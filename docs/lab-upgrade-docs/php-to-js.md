# Converting Image Processing Lab Experiments from PHP to JS

This documentation provides a detailed guide to the process of converting experiments in the Image Processing Lab from PHP to JavaScript. The purpose of this conversion is to enable the deployment of the website as a static web app on storage containers, eliminating the need for server-side scripting.

## Table of Contents

- [Converting Image Processing Lab Experiments from PHP to JS](#converting-image-processing-lab-experiments-from-php-to-js)
  - [Table of Contents](#table-of-contents)
  - [Need for Conversion](#need-for-conversion)
  - [Common Practices](#common-practices)
    - [Removing Unused Files](#removing-unused-files)
    - [Removing PHP Query Tags](#removing-php-query-tags)
    - [PHP Session Management and PHP Variables](#php-session-management-and-php-variables)
    - [Removing Dead Code](#removing-dead-code)
    - [Removing Remaining PHP Code](#removing-remaining-php-code)
    - [Removing AJAX Calls](#removing-ajax-calls)
    - [OpenCV Code Conversion](#opencv-code-conversion)
  - [Importance of Testing](#importance-of-testing)

## Need for Conversion

The transition from PHP to JavaScript aims to achieve a static web application that can be deployed directly on storage containers. By eliminating server-side scripting, the website becomes independent of any runtime environment, enhancing its accessibility and deployability.

## Common Practices

### Removing Unused Files

- Use the VS Code extension "Find Unused Files" to identify and eliminate redundant files. The extension can be downloaded from [here](https://marketplace.visualstudio.com/items?itemName=noxhsxrk.find-unused-files).
- Manually cross-check the usage of files before deletion to ensure no essential components are removed.

### Removing PHP Query Tags

- PHP uses `$_GET["arg"]` syntax for query tags.
- Convert to JavaScript equivalent:
```
function getQueryVariable(variable) {
    var query = window.location.search.substring(1);
    var vars = query.split("&");
    for (var i = 0; i < vars.length; i++) {
        var pair = vars[i].split("=");
        if (decodeURIComponent(pair[0]) == variable) {
            return decodeURIComponent(pair[1]);
        }
    }
    return null;
}
```

### PHP Session Management and PHP Variables

- PHP uses `$_SESSION["arg"]` for session variables.
- Convert to JavaScript global variables:
```
var arg;
```
- PHP global variables follow the same conversion.

### Removing Dead Code

- Identify unreachable code sections through a dry run of the code flow.
- Remove unnecessary code to improve performance and maintainability.

### Removing Remaining PHP Code

- Identify code within `<?PHP ... >` tags.
- Convert to JavaScript manually or use generative AI like ChatGPT. An example query may look like:
    > Convert the following code from PHP to JS. Remove all the PHP and replace them with their JS equivalents <br>
    > \<code\>

### Removing AJAX Calls

- Replace AJAX calls with equivalent JavaScript functions.
- Use ChatGPT for this task:
    > Remove the AJAX call and replace the return value with a JS equivalent - <br>
    > \<ajax call code\> <br>
    > \<code of the php file being called\>
- Extract query tags from AJAX calls to separate JavaScript variables before passing them to the function.

### OpenCV Code Conversion

- Convert C++ experiment logic to JavaScript using the OpenCV.js library.
- Use ChatGPT for this task:
    > Convert the following CPP file to JS using OpenCV.js <br>
    > \<code\>

## Importance of Testing

After each incremental change in the conversion process, it is crucial to thoroughly test the experiment to ensure its accuracy and functionality. Testing should be conducted on the updated web application to verify its stability and correctness.
