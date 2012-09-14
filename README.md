I'm not author of this script
=====================

This is taken from http://inchoo.net/ecommerce/magento/how-to-add-external-javascript-css-file-to-magento/
I just don't like code in blog post and this few lines of code is very helpful for me so I create repo at github with information how to use it

Inchoo-Xternal
=====================

This script is magento extension which give you ability to add external JS and css scripts in head section.

Installation
=====================

- Just copy files.
- edit app/etc/config.xml and add:


```xml
<?xml version="1.0"?>
<config>
    <modules>
        <Inchoo_Xternal>
            <version>1.0.0</version>
        </Inchoo_Xternal>
    </modules>
    <global>    
        <blocks>
            <inchoo_externals>
                <class>Inchoo_Xternal_Block</class>
            </inchoo_externals>
            <page>
                <rewrite>
                    <html_head>Inchoo_Xternal_Block_Html_Head</html_head>
                </rewrite>
            </page>
        </blocks>     
    </global>
    <frontend>
        <layout>
            <updates>
                <inchoo_xternal module="Inchoo_Xternal">
                    <file>inchoo_xternal.xml</file>
                </inchoo_xternal>
            </updates>
        </layout>
    </frontend>
</config>
```

- In your configurations (for example layout/page.xml) use

```xml
<action method="addExternalItem"><type>external_js</type><name>http://ajax.googleapis.com/ajax/libs/jquery/1.8.1/jquery.min.js</name><params/></action>
<action method="removeExternalItem"><type>external_css</type><name>http://yui.yahooapis.com/2.8.2r1/build/fonts/fonts-min.css</name><params/></action>
```