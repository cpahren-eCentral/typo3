# Styla TYPO3 Plugin
This typo3 plugin allows to run the Styla content hub and / or landing pages with full SEO integration.

## Requirements
TYPO3 >= 7.6.31  
PHP >= 5.5  
MySQL >= 5.5

##Installation
* Move the extension folder `ec_styla` to `/typo3conf/ext/`
* Inside the TYPO3 backend, go to Extensions and activate ec_styla

## Configuration
Include the Typoscript template 'Styla Integration (ec_styla)' to your root page template. You may use the provided
default or set your own configuration. Options can be configured for either the whole pagetree or the individual pages. 

#### Page Configuration
Necessary meta elements are provided by STYLA. This configuration has to be
done for every page on which the content hub plugin will be displayed and will hide meta elements generated by TYPO3.

    page.meta.robots =
    config.noPageTitle = 2
    
Please note that there are issues with hiding the page title in some versions of TYPO3. Further information is available
in issue [#85720](https://forge.typo3.org/issues/85720) of the TYPO3 core bug tracker.
    
### Extension Configuration
Within the plugin configuration the rootpath to the styla content needs to be set up.
    
## Plugins
You can add STYLA Plugins via the 'Add Content' option of the page module. 

### Content Hub
The content hub plugin will display a single content hub. You only need to provide the content hub id and let STYLA do the
magic. Please make sure the page title corresponds to your plugin.tx_ecstyla_contenthub.settings.contenthub_segment setting.

### Teaser
The Teaser plugin allows you to feature a number of stories from your STYLA content hub. You can set the number of items 
to be displayed, the size of the teaser images as well as the display mode. Available display modes are:
* List
* Tiles
* Cards
* Horizontal

## Signal Slots
The extension provides two signal slots: beforeProcessingSeoContent and beforeCheckingForRootPath. You can find
out more information about signal slots in the [official TYPO3 documentation](https://docs.typo3.org/typo3cms/CoreApiReference/ApiOverview/Hooks/Concept/Index.html). 

## Caching
TYPO3 will cache STYLA related content for up to 60 Minutes by default. You can clear the cache anytime by using TYPO3s 'Clear all
caches' option within the TYPO3 backend.
