# Configuring Profiles, Adding Custom Columns

## Adding Column: Delta Time 

- Adding Delta time to column without deleting the Default time.
- Delta time: the amount of time in between packets.

Edit > Preferences > Appearance > Columns > +; Change Title: Delta; Change Type: Delta time displayed > OK

<p align="center"> <img src="https://i.imgur.com/567q3Jr.png" height="90%" width="90%" alt=""/>

Drag Delta column next to Time column

<p align="center"> <img src="https://i.imgur.com/DzJxI1o.png" height="90%" width="90%" alt=""/>

#

## Adding Column: TTL

- Time to Live: value that dictates how long a package of data should exist on a network before being discarded.

Look at the second section wireshark > Expand Internet Protocol Version 4 > Right click: Time to Live > Apply as Column

<p align="center"> <img src="https://i.imgur.com/DxZdvin.png" height="90%" width="90%" alt=""/>

Time to Live Column will be added:

<p align="center"> <img src="https://i.imgur.com/JEcTV3S.png" height="90%" width="90%" alt=""/>

#

# Coloring Traffic

- Can Disable Coloring Rule by clicking This Icon on the top menu bar:

<p align="center"> <img src="https://i.imgur.com/3oCzH31.png" height="90%" width="90%" alt=""/>

#

- Adding Filter button: TCP SYNs
- tcp.flags.syn==1

<p align="center"> <img src="https://i.imgur.com/a69DYQk.png" height="90%" width="90%" alt=""/>

#

Adding Color rule for tcp.flags.syn==1

- View > Coloring Rules

<p align="center"> <img src="https://i.imgur.com/3krrfjd.png" height="90%" width="90%" alt=""/>

- "+" > Change Name: TCP SYNS; Change Filter: tcp.flags.syn==1 > Background > Choose a color (I chose Bright Green)

<p align="center"> <img src="https://i.imgur.com/aHA6clD.png" height="90%" width="90%" alt=""/>

- Drag TCP SYNs below Bad TCP because the list is in order of priority from Top to bottom.

<p align="center"> <img src="https://i.imgur.com/tOi2iXr.png" height="90%" width="90%" alt=""/>

Result: 

- With TCP SYNs filter on:
<p align="center"> <img src="https://i.imgur.com/QOulqeE.png" height="90%" width="90%" alt=""/>

- Without TCP SYNs filter on:
<p align="center"> <img src="https://i.imgur.com/s8jq5Pi.png" height="90%" width="90%" alt=""/>



  
