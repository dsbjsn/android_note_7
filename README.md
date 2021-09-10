# 等比例缩放图片
```
    /**
     * 返回等比例缩放后的图片
     *
     * @param pBitmap    图片
     * @param pMaxWidth  最大图片宽度
     * @param pMaxHeight 最大图片高度
     * @return
     */
    public static Bitmap getScaleBitmap(Bitmap pBitmap, int pMaxWidth, int pMaxHeight) {
        if (pBitmap == null) {
            return null;
        }
        if (pBitmap.getWidth() > pMaxWidth || pBitmap.getHeight() > pMaxHeight) {
            float s_w = (float) pBitmap.getWidth() / pMaxWidth;
            float s_h = (float) pBitmap.getHeight() / pMaxHeight;
            float max_s = Math.max(s_w, s_h);
            return Bitmap.createScaledBitmap(pBitmap, (int) (pBitmap.getWidth() / max_s), (int) (pBitmap.getHeight() / max_s), false);
        } else {
            return pBitmap;
        }
    }
```
