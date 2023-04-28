# CSS

- margin is preset to have 8px. you can remove this by simple saying margin: 0px.

# root 

:root{
  --page-bg: white;
  --primary: blue;
}

root is an easy way to create css variables.

can use 'var(--)' to use variables

# flex

can use flex tools on dev tools to mess around directly with web page

min-height can be used to set a height

gap utility can be used to make space between elements

# Box model

Content / padding / border / margin

rem is correlated to the root parent element.
em is correlated to the closest parent.

nothing has a default max width, you have to set it. Even d-flex wont put things side by side IF there is no room.

box-sizing: content-box / border-box; usually needed for margin issues. It basically includes margin and padding in the percentages.

# Button

border: none; gets rid of all the preset styling

# Hover 
drop-shadow()

## background-image: url(the link)

can use background-position: center; to center image.
background-size: cover;
background-repeat: none;

## image

instead of background we use object.
object-fit: cover;
object-position: center;

# you can use text-center on images because they are inline. USING D-FLEX ON COLUMNS IS NOT GOOD!!!

# glassmorphism

glassmorphism generator allows you to create a slightly transparent card.

# elevation
elevation and be used instead of box shadow

# media rules

@media (max-width: 768px) {

}

put parameters in the parenthesis and everything that takes affect when those parameters are met.








