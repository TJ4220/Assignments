```python
import tkinter
def calculate_mpg():
  gallons = float(gallons_entry.get()) 
  miles = float(miles_entry.get()) 
  mpg = miles / gallons   # my formula
  result_label.config(text=f"MPG: {mpg:.2f}")  # showes the MPG
root = tkinter.Tk()  # makes the window
root.title ("MPG Calculator")
root.resizable (False, False)
gallons_text = tkinter.Label(root, text="Gallons in the tank" )  #labeling the text 
gallons_text.pack(padx=10, pady=4)
gallons_entry = tkinter .Entry(root, width=50)   #input for the gallons
gallons_entry.pack(padx=10, pady=2)
gallons_entry.focus()
miles_text = tkinter.Label(root, text="Miles on a full tank")
miles_text.pack(padx=10, pady=4)
miles_entry = tkinter.Entry(root, width=50)
miles_entry.pack(padx=10, pady=2)
result_label = tkinter.Label(root, text="MPG: -") #showes the answer
result_label.pack(padx=10, pady=8)
calculate_button = tkinter.Button(
  root,
  text="Calculate MPG",
  command=calculate_mpg
)
calculate_button.pack(pady=6)  
quit_button = tkinter.Button(    #makes the quite button
  root,
  text="Quit",
  command=root.destroy
)
quit_button.pack(pady=(0, 10))
root.mainloop()
``` 
