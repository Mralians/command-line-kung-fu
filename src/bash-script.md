## Bash Script Tips

1. readarray

   ```bash
   #!/usr/bin/env bash
   
   readarray NAMES<<EOF
   anna
   elisabeth
   john
   EOF
   echo "${NAMES[0]}"
   ```

   ```bash
    #!/usr/bin/env bash
    
    readarray -t _sounds_list < <(find "${sounds_dir}" \( -iname "*.mp3" -o -iname "*.m4a" -o -iname "*.ogg" \) -printf '%P\n')
   ```

2. 
   ```bash
   #!/usr/bin/env bash
   
   
   family=$(awk '/cpu family/ {print $NF;exit}' /proc/cpuinfo)
   
   if (( family != 6 ));then
       echo >&2 "WARNING: CPU family $family not recognized (not Intel?):"
   fi
   ```

3. 
