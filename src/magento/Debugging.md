---
name: Debugging
menu: Magento
---

# Debugging

## Logging

locate the file at: 
`vendor/magento/framework/Event/Manager.php`

append this into `dispatch` function

`file_put_contents(BP . '/var/log/events.log', "$eventName\n", FILE_APPEND);`

## Resolver

### Backend Controller Resolver 

`\Magento\Backend\App\Router::matchAction` 


