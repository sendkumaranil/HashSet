# HashSet
<b>How HashSet implemented internally?</b>

Actually HashSet implemented in HashMap internally.It is using put method of HashMap and enter the value as key and Constant value as value.

      public class HashSet<E> extends AbstractSet<E>
			    implements Set<E>, Cloneable, java.io.Serializable{
          
			 static final long serialVersionUID = -5024744406713321676L;
		 
			 private transient HashMap<E,Object> map;
		 
			 // Dummy value to associate with an Object in the backing Map
			 private static final Object PRESENT = new Object();
			 
			 public HashSet() {
					map = new HashMap<E,Object>();
			}

			 //add method of HashSet
			 public boolean add(E e) {
					return map.put(e, PRESENT)==null;
			}
			
			//remove method of HashSet
			public boolean remove(Object o) {
					return map.remove(o)==PRESENT;
			}
		}
