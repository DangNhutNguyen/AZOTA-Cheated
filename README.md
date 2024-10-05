# AZOTA Exam Bypass Instructions

This guide provides steps to disable event listeners during an Azota exam.

## Steps:

1. **Open the Azota exam page.**
   
2. **Press `Control + Shift + I`** to open the Developer Tools. This will bring up the console where you can enter custom scripts.

3. **Navigate to the Console tab** in the Developer Tools.

4. **Copy and paste the following JavaScript code** into the console:

    ```javascript
    function removeAllEventListeners(target, eventTypes) {
        eventTypes.forEach(eventType => {
            const listeners = getEventListeners(target)[eventType];
            if (listeners) {
                listeners.forEach(listener => {
                    target.removeEventListener(eventType, listener.listener);
                });
            }
        });
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

    console.log("Removed all - Done by NGUYEN HUYNH DANG NHUT");
    ```

5. **Hit Enter** to execute the script.

6. Once the script is executed, you'll see the message `Removed all - Done by NGUYEN HUYNH DANG NHUT` in the console, confirming that all event listeners have been removed.

## Notes:
- This script removes certain event listeners from the Azota exam page, which may prevent certain restrictions like monitoring or alerts triggered by specific actions.
- Use this responsibly and only for educational purposes.

**Disclaimer:** The author is not responsible for any misuse of this script.
