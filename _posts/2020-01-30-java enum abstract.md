java enum abstract
===

```
public enum Status {
  BEFORE {
    public boolean getDeletable() {
      return true;
  }

  STOP {
    public boolean getDeletable() {
      return false;
  }

  public abstract boolean getDeletable();
}


  if(Status.getDeleteable()) {
    블라블라....
  }

```