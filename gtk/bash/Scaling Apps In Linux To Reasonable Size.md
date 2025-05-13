The purpose of the below bash function is to set an apps default scale to 2. My reasoning for this is because some Linux apps are not scaled properly by default despite global settings that should allow them all to be the same size.

```bash
# Sets scale to 2 for any application run from the terminal 
function scaled() {
    # Check to see if argument is provided
    if [ -z "$1" ]; then
        echo "Usage: scaled <application_name>"
        return 1
    fi

    local app_name="$1"

    # Shift to remove the first argument
    shift


    # Run the application with a scale factor of 2
    env QT_SCALE_FACTOR=2 "$app_name" "$@"
}
```