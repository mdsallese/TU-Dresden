from tkinter import *
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.backends.backend_tkagg import FigureCanvasTkAgg, NavigationToolbar2Tk

root = Tk()

def plot():
    
    np.random.seed(3)
    
    width, height = 200, 200
    
    wavy =  int(e2.get())
    
    x, y = np.meshgrid(np.arange(width),np.arange(height))
    
    # noise_w = n1.get()  #0.5
    # noise_i = n2.get() #0.15
    
    noise_w = 0.5 #bigger noise (waviness)
    noise_i = 0.15 #smaller noise
    
    period = int(e1.get())
    
    # xyz = (noise_w*np.random.random(1))*np.sin(2*np.pi*(y + period *wavy* np.sin(2*np.pi* x /(period*25)))/period) + noise_i*np.random.random((height,width))
    xyz = (noise_w*np.random.random(1))*np.sin(2*np.pi*(y + period *wavy* np.sin(2*np.pi* x /(period*25)))/period) + noise_i*np.random.random((height,width))
    
    ax[0].imshow(xyz)
    ax[0].set_title('3D image')
    ax[1].clear()
    ax[1].plot(xyz[:,100])
    ax[1].set_title('Profile')
    ax[1].set_xlim(0, 200)
    ax[1].set_box_aspect(1)
    canvas.draw()

fig, ax = plt.subplots(1, 2, figsize=(10, 5))

frame = Frame()
l1 = Label(text='First GUI')
l1.config(font=("Arial",15))
l1.pack()

canvas = FigureCanvasTkAgg(fig, master=root)
canvas.get_tk_widget().pack()

toolbar = NavigationToolbar2Tk(canvas, frame, pack_toolbar=False)
toolbar.update()
toolbar.pack()

b1 = Button(root,text="Plot", command = plot).pack()
l2 = Label(root, text="Period [um]:")
l3 = Label(root, text="Wavy [level]:")

e1 = Entry(root)
e1.pack()
e1.insert(0, "period value [um]")
# e1.grid(row=0, column=1)
e2 = Entry(root)
e2.pack()
e2.insert(0, "wavy [value]:")

frame.pack()

root.mainloop()
