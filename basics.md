COPY MODULE

 - name: Create a new file with permissions
   file:
      path: "/your path"
      state: touch
      mode: 0755
      owner: test