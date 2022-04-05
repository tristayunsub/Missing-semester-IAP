ad hoc approach could take version control

trach changes give that folder a timestamp, ,


top -level directory

root and foo is tree(folder) and other txt files are "blob" file

root

- foo
      - bar.txt=hello world

- baz.txt = "git is awesome"

git is more acyclig graph fancy system


each every state points back to which state preceded
     1           2                 3 : +features                      = as an ID like for a 4af323cds .... 
     O     <-     O     <-        O             <-           0   :both featureand bug fix   <-- O fix-bug
  
                  |              4:bugfix but not the feature
                  | ------------     O 
                                 
                
                1. author: anish, message:
                
         type bob = array<bytes>
         type tree = map<string, subtree | blob>
         type commit = struct {
              parents array< commit>
              meta data like author: string
              message:string
              snapshot: tree- its actually ID of the tree
      
      how git actually stores and addresses this actual data like  on disk 
      
      
      type object = blob | tree | commit
      
      objects = map<string, object>
      
      def store(o)
          id=shal(o)
          objects[id]=o
          
          hash function turn big data to short string
      
      def load(id)
         return object[id]
         
         
        references = map<string, string>
              fix-encoding -- bug its human readable name
              references are immuatable
              
 

![git_graph](https://user-images.githubusercontent.com/75001605/161687535-b79e65fb-700a-45e9-a28a-7cfaeb395709.png)

            
