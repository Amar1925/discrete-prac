#include <iostream>
#include <set>
using namespace std;

class MySet {
private:
  set<int> elements;

public:
  MySet() {}

  void add(int value) {
    elements.insert(value);
  }

  void printPowerSet() {
    int n = elements.size();
    set<set<int>> powerSet;
    for (int i = 0; i < (1 << n); i++) {
      set<int> subset;
      for (int j = 0; j < n; j++) {
        if (i & (1 << j)) {
          subset.insert(*next(elements.begin(), j));
        }
      }
      powerSet.insert(subset);
    }

    for (auto subset : powerSet) {
      for (auto element : subset) {
        cout << element << " ";
      }
      cout << endl;
    }
  }

  void printUnion(const set<int>& s1, const set<int>& s2) {
    set<int> unionSet;
    for (auto element : s1) {
      unionSet.insert(element);
    }
    for (auto element : s2) {
      unionSet.insert(element);
    }

    for (auto element : unionSet) {
      cout << element << " ";
    }
    cout << endl;
  }

  void printIntersection(const set<int>& s1, const set<int>& s2) {
    set<int> intersectionSet;
    for (auto element : s1) {
      if (s2.find(element) != s2.end()) {
        intersectionSet.insert(element);
      }
    }

    for (auto element : intersectionSet) {
      cout << element << " ";
    }
    cout << endl;
  }

  bool isElementPresent(int element) {
    return elements.find(element) != elements.end();
  }

  bool isSubset(const set<int>& subset) {
    for (auto element : subset) {
      if (elements.find(element) == elements.end()) {
        return false;
      }
    }

    return true;
  }

  set<int> getComplement(const set<int>& universalSet) {
    set<int> complement;
    for (auto element : universalSet) {
      if (elements.find(element) == elements.end()) {
        complement.insert(element);
      }
    }

    return complement;
  }

  set<int> getSetDifference(const set<int>& s1, const set<int>& s2) {
    set<int> difference;
    for (auto element : s1) {
      if (s2.find(element) == s2.end()) {
        difference.insert(element);
      }
    }

    return difference;
  }

  set<int> getSymmetricDifference(const set<int>& s1, const set<int>& s2) {
    set<int> difference;

    for (auto element : s1) {
      if (s2.find(element) == s2.end()) {
        difference.insert(element);
      }
    }

    for (auto element : s2) {
      if (s1.find(element) == s1.end()) {
        difference.insert(element);
      }
    }

    return difference;
  }

  void printCartesianSet(const set<int>& s2, const set<int>& s3) {

    for (const auto& x : s2) {
      for (const auto& y : s3) {
        cout << x << " " << y << endl;
      }
    }
    cout << endl;
  }
};

int main() {

  MySet s;
  s.add(1);
  s.add(2);
  s.add(3);
  set<int> uniset = {1,2,3,4,5,6,7,8,9};
  set<int> s2 = {1,2,3,4};
  set<int> s3 = {0,3,4,6,7};
  set<int> subset = {1,2};


    int choice;

  do {
    cout << "Menu:" << endl;
    cout << "1. Check if an element is present" << endl;
    cout << "2. Print power set" << endl;
    cout << "3. Check if a set is a subset" << endl;
    cout << "4. Print union & intersection of two sets" << endl;
    cout << "5. Get complement of a set" << endl;
    cout << "6. Get set difference & symmetric difference" << endl;
    cout << "7. Print Cartesian product of two sets" << endl;
    cout << "8. Quit" << endl;
    cout << "Enter your choice: ";
    cin >> choice;
    
    switch (choice) {
      case 1: {
        int element;
        cout << "Enter the element to check: ";
        cin >> element;
        bool present = s.isElementPresent(element);
        cout << (present ? "Element is present" : "Element is not present") << endl;
        break;
      }
      case 2: {
        s.printPowerSet();
        break;
      }
      case 3: {
        bool subsetOfMySet = s.isSubset(subset);
        cout << (subsetOfMySet ? "The given set is a subset" : "The given set is not a subset") << endl;
        break;
      }
      case 4: {
        cout << "Union of S2 & S3:"; 
        s.printUnion(s2, s3);
        cout <<endl;
        cout << "Intersection of S2 & S3:"; 
        s.printIntersection(s2, s3);
        cout <<endl;
        break;
      }
      case 5: {
            cout<< "Complement is :" << endl;
            set<int> complement = s.getComplement(uniset);

            for (auto element: complement) {
                cout << element << " ";
            }
            cout << endl;
        break;
      }
      case 6: {
            cout << "Set difference of S2 & S3:" << endl; 
            set<int> set_difference = s.getSetDifference(s2, s3);
            for (auto element: set_difference) {
                cout << element << " ";
            }

            cout << "Symmetric set difference of S2 & S3:" << endl; 
            set<int> sym_set_difference = s.getSymmetricDifference(s2, s3);
            for (auto element: sym_set_difference) {
                cout << element << " ";
            }
        break;
      }
      case 7: {
        cout << "Cartesian products are:" << endl;
        s.printCartesianSet(s2, s3);
        break;
      }
      case 8: {
        cout << "Exiting the program..." << endl;
        break;
      }
      default: {
        cout << "Invalid choice. Please try again." << endl;
        break;
      }
    }

    cout << endl;
  } while (choice != 8);

  return 0;
}
