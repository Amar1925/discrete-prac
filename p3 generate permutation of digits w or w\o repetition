#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

// Function to generate permutations of a given set of digits
void generatePermutations(vector<int>& digits, vector<int>& permutation, vector<bool>& used, int n) {
    // Base case: if the permutation is complete, print it
    if (permutation.size() == n) {
        for (int digit : permutation) {
            cout << digit << " ";
        }
        cout << endl;
        return;
    }

    // Recursive case: generate permutations
    for (int i = 0; i < n; i++) {
        // If the digit is not used in the current permutation
        if (!used[i]) {
            // Add the digit to the current permutation
            permutation.push_back(digits[i]);
            used[i] = true;

            // Recursive call to generate remaining permutations
            generatePermutations(digits, permutation, used, n);

            // Remove the last added digit from the current permutation
            permutation.pop_back();
            used[i] = false;
        }
    }
}

// Function to generate permutations of a given set of digits (with repetition)
void generatePermutationsWithRepetition(vector<int>& digits, vector<int>& permutation, int n, int k) {
    // Base case: if the permutation is complete, print it
    if (permutation.size() == k) {
        for (int digit : permutation) {
            cout << digit << " ";
        }
        cout << endl;
        return;
    }

    // Recursive case: generate permutations
    for (int i = 0; i < n; i++) {
        // Add the digit to the current permutation
        permutation.push_back(digits[i]);

        // Recursive call to generate remaining permutations
        generatePermutationsWithRepetition(digits, permutation, n, k);

        // Remove the last added digit from the current permutation
        permutation.pop_back();
    }
}

int main() {
    int n, k;
    cout << "Enter the number of digits: ";
    cin >> n;

    vector<int> digits(n);
    cout << "Enter the digits: ";
    for (int i = 0; i < n; i++) {
        cin >> digits[i];
    }

    cout << "Permutations without repetition:" << endl;
    vector<int> permutation;
    vector<bool> used(n, false);
    generatePermutations(digits, permutation, used, n);

    cout << "Permutations with repetition (k): ";
    cin >> k;
    cout << "Permutations with repetition:" << endl;
    permutation.clear();
    generatePermutationsWithRepetition(digits, permutation, n, k);

    return 0;
}
