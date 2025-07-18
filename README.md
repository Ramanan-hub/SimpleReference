package com.mrk.john.bookapplication.bookproject.repositories;
import java.util.ArrayList;
import java.util.List;
import com.mrk.john.bookapplication.bookproject.models.Book;
import com.mrk.john.bookapplication.bookproject.models.BookCRUD;

public class BookRepository implements BookCRUD {
private List<Book> books=null;
public BookRepository() {
super();
// TODO Auto-generated constructor stub
books = new ArrayList<>();
books.add(new Book(1L,"Java Core","Murugan",2450.00));
books.add(new Book(2L,"Spring Boot","Shiva",3250.00));
books.add(new Book(3L,"Angular","Devi",4350.00));
books.add(new Book(4L,"HTML","Lakshmi",4950.00));
}

@Override
public void createBook(Book book) {
books.add(book);

}

@Override
public List<Book> readBooks() {

return books;
}

@Override
public void updateBook(Book book) {
int index =0;
  for(int i=0;i<books.size();i++){
    if(books.get(i).getBno() == book.getBno()){
      index = i;
    }
  }
  books.set(index,book);

}

@Override
public void deleteBook(Long bno) {
int index =0;
  for(int i=0;i<books.size();i++){
    if(books.get(i).getBno() == bno){
      index = i;
    }
  }
  books.remove(index);

}

@Override
public Book readBook(Long bno) {
int index =0;
  for(int i=0;i<books.size();i++){
    if(books.get(i).getBno() == bno){
      index = i;
    }
  }
  return books.get(index);
}

}
