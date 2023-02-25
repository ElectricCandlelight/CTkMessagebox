# CTkMessagebox
**A modern and fully customizable messagebox for [customtkinter](https://github.com/TomSchimansky/CustomTkinter)**

### Features:
- Customize all elements inside the messagebox
- Add custom icons or images
- Spawns at center of the screen
- Add multiple buttons according to your wish
- No ugly looking header or borders
- Comes with **5 default icons**
- Draggable window

## Installation
```
pip install CTkMessagebox
```

[<img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/Akascape/CTkMessagebox?&color=green&label=Source%20Code&logo=Python&logoColor=yellow&style=for-the-badge"  width="300">](https://github.com/Akascape/CTkMessagebox/archive/refs/heads/main.zip)

## How it looks?
![Screenshot](https://user-images.githubusercontent.com/89206401/221258593-75058878-b598-40c3-828a-1d44a6cefb73.jpg)

## Example
```python
from CTkMessagebox import CTkMessagebox
import customtkinter

def show_info():
    # Default messagebox for showing some information
    CTkMessagebox(title="Info", message="This is a CTkMessagebox!")

def show_checkmark():
    # Show some positive message with the checkmark icon
    CTkMessagebox(message="CTkMessagebox is successfully installed.",
                  icon="check", option_1="Thanks")
    
def show_error():
    # Show some error message
    CTkMessagebox(title="Error", message="Something went wrong!!!", icon="cancel")
    
def show_warning():
    # Show some retry/cancel warnings
    msg = CTkMessagebox(title="Warning Message!", message="Unable to connect!",
                  icon="warning", option_1="Cancel", option_2="Retry")
    
    if msg.get()=="Retry":
        show_warning()
        
def ask_question():
    # get yes/no answers
    msg = CTkMessagebox(title="Exit?", message="Do you want to close the program?",
                        icon="question", option_1="Cancel", option_2="No", option_3="Yes")
    response = msg.get()
    
    if response=="Yes":
        app.destroy()       
    else:
        print("Click 'Yes' to exit!")
              
app = customtkinter.CTk()
app.rowconfigure((0,1,2,3,4,5), weight=1)
app.columnconfigure(0, weight=1)
app.minsize(200,250)

customtkinter.CTkLabel(app, text="CTk Messagebox Examples").grid(padx=20)

customtkinter.CTkButton(app, text="Check CTkMessagebox", command=show_checkmark).grid(padx=20, pady=10, sticky="news")
customtkinter.CTkButton(app, text="Show Info", command=show_info).grid(padx=20, pady=10, sticky="news")
customtkinter.CTkButton(app, text="Show Error", command=show_error).grid(padx=20, pady=10, sticky="news")
customtkinter.CTkButton(app, text="Show Warning", command=show_warning).grid(padx=20, pady=10, sticky="news")
customtkinter.CTkButton(app, text="Ask Question", command=ask_question).grid(padx=20, pady=(10,20), sticky="news")

app.mainloop()

```

## OPTIONS
  | Parameters  | Description |
  | -------- | ----------- |
  | _width_ | width of the window in px (optional) |
  | _height_ | height of the window in px (optional) |
  | _fg_color_ | forground color of the messagebox [middle portion] |
  | _bg_color_  | background color of the messagebox |
  | **_title_** | title of the messagebox |
  | **_message_** | main message of the messagebox which will be shown at the center |
  | **_option_1_** | the text of the first button [Default is 'OK'] |
  | **_option_2_** | the text of the second button |
  | **_option_3_** | the text of the last button |
  | _button_color_ | color of the buttons |
  | _text_color_ | color of the message-text |
  | _button_text_color_ | color of the button-text |
  | _button_width_ | width of the buttons in px |
  | _cancel_button_color_ | color of the **close** button |
  | **_icon_** | icon that will be shown in the messagebox [Default is 'info'] |
  | _icon_size_ | define the size of the icon image manually (tuple) |
  | _corner_radius_ | corner roundness of the messagebox window |
  | _font_ | font of the messagebox text (tuple) |

### Icons

**Default icons:**

![icons](https://user-images.githubusercontent.com/89206401/221258403-aafea575-856e-4f4e-b3af-f995785c9879.png)

(*These icons are created by me using Paint.Net, free to use!*)

**For custom images, just use `icon="path_to_the_image.png"`**

## That's all, hope it will help in UI development!
