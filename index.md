# meme R code

```{r}
library(magick)
# square one
meme <- image_read("https://c-ssl.duitang.com/uploads/item/201811/04/20181104121907_VMBCW.jpeg")
meme <- image_annotate(meme, "Tears overflow\nthe screen", size = 30, color = "red", boxcolor = "pink",
                 degrees = 60, location = "+50+100")

# square two
text <- image_blank(width = 400, 
                       height = 400, 
                       color = "#000000") %>%
  image_annotate(text = "When you find out you have\nthree assignments due tomorrow",
                 color = "#FFFFFF",
                 size = 20,
                 font = "Impact",
                 gravity = "center")


# first using the approach we used above
meme <- image_append(c(meme, text))

# making the whole thing!

# using another approach
image_append(meme, stack = TRUE) %>%
  image_scale(800)
image_write(meme, "my_meme.png")
```

## information about the meme

1. motivation
   * I want to make an meme to show the real situation that some students begin to write assignments just before the deadline :)

2. how your meme is new/original
   * Add text on images referenced from web pages, and background fills for text
   * Change text color and position
