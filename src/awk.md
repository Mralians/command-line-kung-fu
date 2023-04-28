# Awk

1. Delete extra spaces
   ```bash
   cat text
   #zstdmt (1)           - zstd, zstdmt, unzstd, zstdcat - Compress or decompress .zst files
   cat text | awk '$3="-";print $0'
   #zstdmt (1) - zstd, zstdmt, unzstd, zstdcat - Compress or decompress .zst files
   ```

   