- Stub needs lots of code to maintain the test functioning. Mockito can create mocks which will require less for unit testing.

- implementation: 
    - SomeService someServiceMock = mock(SomeService.class);
    - someServiceMock.retrieveAllData() => new int[] {2,4,15,77}
    - when(someServiceMock.retrieveAllData()).thenReturn(new int[]{2,4,15,77});
    - someBusinessImpl businessImpl = new SomeBusinessImpl(someServiceMock);
  
- int result = businessImpl.findTheGreatestFromAllData();
  assertEquals(77, result);
  
Can create multiple tests with Mockito.

- Mockito annotations:
  ```
  @Mock
  SomeService someServiceMock;
  @InjectMocks
  SomeBusinessImpl businessImpl;
  
  @RunWith(MockitoJUnitRunner.class)
  public class SomeBusinessMockAnnotationsTest {}
  
  @Test
  public void testFindTheGreatest(){
      when(someServiceMock.retrieveAllData()).thenReturn(new int[]{2,4,15,77});
      assertEquals(77, businessImpl.findTheGreatestFromAllData(););
  }
  ```

- Mocking List Interface
    ```
  @Test
  public void test() {
      List listMock = mock(List.class);
      when(listMock.size()).thenReturn(10);
      assertEquals(10, listMock.size());
  }
  
  @Test
  public void testMultipleReturns() {
      List listMock = mock(List.class);
      when(listMock.size()).thenReturn(10).thenReturn(20);
      assertEquals(10, listMock.size());
      assertEquals(20, listMock.size());
  }
  
  @Test
  public void testGet() {
      List listMock = mock(List.class);
      when(listMock.get(0)).thenReturn("SomeString");
      assertEquals("SomeString", listMock.get(0));
      assertEquals(null, listMock.get(1));
  }
  ```
  
  
