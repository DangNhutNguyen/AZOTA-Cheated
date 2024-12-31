# AZOTA & K12 Online Exam Bypass Instructions

This guide provides steps to disable event listeners during an Azota & K12 Online exam.
This script used to bypass the restriction by other test to cheat out.

## Applicable Pages:
This script is intended to be used on the following Azota exam pages:

- **Azota pages**: `https://azota.vn/*`
- **K12 Online**: `https://k12online.vn/*`

## Steps:

1. **Allow pasting in the console (If need)**

    In some browsers, pasting directly into the console is disabled for security reasons. To enable it, type the following into the console first and hit Enter:

    ```javascript
    allow pasting
    ```

2. **Copy the code below before entering the exam**:
    **AZOTA**
   
    ```javascript
    function removeAllEventListeners(target, eventTypes) {
        try {
            eventTypes.forEach(eventType => {
                const listeners = getEventListeners(target)[eventType];
                if (listeners) {
                    listeners.forEach(listener => {
                        target.removeEventListener(eventType, listener.listener);
                    });
                }
            });
            console.log("Removed all - Done by NGUYEN HUYNH DANG NHUT");
        } catch (error) {
            console.error("An error occurred: Could not remove event listeners. Error details:", error);
        }
    }

    const eventTypes = [
        'beforeunload', 'blur', 'click', 'DOMContentLoaded', 'hashchange',
        'keydown', 'load', 'locationchange', 'message', 'mousedown',
        'orientationchange', 'popstate', 'resize', 'scroll', 'touchstart',
        'visibilitychange'
    ];

    // Remove event listeners from window and document
    removeAllEventListeners(window, eventTypes);
    removeAllEventListeners(document, eventTypes);
    ```
    **K12 Online**
   
    ```javascript
    function removeAllEventListeners(target, eventTypes) {
        try {
            eventTypes.forEach(eventType => {
                const listeners = getEventListeners(target)[eventType];
                if (listeners) {
                    listeners.forEach(listener => {
                        target.removeEventListener(eventType, listener.listener);
                    });
                }
            });
            console.log("Removed all - Done by NGUYEN HUYNH DANG NHUT");
        } catch (error) {
            console.error("An error occurred: Could not remove event listeners. Error details:", error);
        }
    }
    
    const eventTypes = [
        'DOMContentLoaded', 'ajaxError', 'ajaxStart', 'ajaxStop', 'auxclick',
        'beforeunload', 'blur', 'change', 'click', 'confirmation', 
        'contextmenu', 'focus', 'focusin', 'focusout', 'hashchange',
        'keydown', 'load', 'pagehide', 'pageshow', 'popstate',
        'readystatechange', 'resize', 'scroll', 'unload', 'visibilitychange'
    ];
    
    // Remove event listeners from window and document
    removeAllEventListeners(window, eventTypes);
    removeAllEventListeners(document, eventTypes);
     ```
4. **Open the Azota or K12 Online exam page** you are currently on (`https://azota.vn/*` or `https://k12online.vn/*`).
   
5. **Press `Ctrl + Shift + I`** to open the Developer Tools. This will bring up the console where you can enter custom scripts.

| Operating System | Keys |
| :----------------: | :----: |
| macOS | <kbd>alt</kbd><kbd>cmd</kbd><kbd>i</kbd> |
| Windows | <kbd>ctrl</kbd><kbd>shift</kbd><kbd>i</kbd> |
| Linux | <kbd>ctrl</kbd><kbd>shift</kbd><kbd>i</kbd> |

5. **Navigate to the Console tab** in the Developer Tools.

6. **Paste the copied JavaScript code** into the console.

7. **Hit Enter** to execute the script.

    Once the script is executed successfully, you'll see the message `Removed all - Done by NGUYEN HUYNH DANG NHUT` in the console, confirming that all event listeners have been removed.

8. **Error Handling**: 
   - If the script encounters an error while removing the event listeners, it will display an error message in the console:  
     `An error occurred: Could not remove event listeners. Error details: [error details]`.

## Notes:
- This script removes certain event listeners from the Azota & K12 Online exam page, which may prevent certain restrictions like monitoring or alerts triggered by specific actions.
- Yet, I've tested this script in command and the error is: You couldn't Accepted to submit your test until the time is up in K12 Online, but the Azota could used easily.
- You can use this responsibly and only for educational purposes.

**Disclaimer:** The author is not responsible for misusing this script.
