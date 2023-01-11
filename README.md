import cv2

# read the image
image = cv2.imread("image_with_watermark.jpg")

# define the region of the image that contains the watermark
x, y, w, h = (50, 50, 200, 100)

# create a mask that covers the watermark
mask = cv2.imread("watermark_mask.jpg", 0)

# apply the mask to the image
result = cv2.inpaint(image, mask, 3, cv2.INPAINT_TELEA)

# save the result
cv2.imwrite("image_without_watermark.jpg", result)
