#include <iostream>

template<typename T, size_t N>
class FixedArray {
private:
    T data[N];

public:
    FixedArray() {
        for (size_t i = 0; i < N; ++i) {
            data[i] = T();
        }
    }

    FixedArray(const T (&arr)[N]) {
        for (size_t i = 0; i < N; ++i) {
            data[i] = arr[i];
        }
    }

    FixedArray& operator=(const FixedArray& other) {
        if (this != &other) {
            for (size_t i = 0; i < N; ++i) {
                data[i] = other.data[i];
            }
        }
        return *this;
    }

    FixedArray& operator+=(const FixedArray& other) {
        for (size_t i = 0; i < N; ++i) {
            data[i] += other.data[i];
        }
        return *this;
    }

    bool operator==(const FixedArray& other) const {
        for (size_t i = 0; i < N; ++i) {
            if (data[i] != other.data[i]) 
                return false;
        }
        return true;
    }

    T& operator[](size_t index) {
        return data[index]; 
    }

    void print() const {
        std::cout << "[";
        for (size_t i = 0; i < N; ++i) {
            std::cout << data[i];
            if (i < N - 1) std::cout << ", ";
        }
        std::cout << "]" << std::endl;
    }
};

int main() {
    FixedArray<int, 5> a;
    int init[5] = {10, 20, 30, 40, 50};
    FixedArray<int, 5> b(init);
    FixedArray<int, 5> c = b;

    a = b;
    a += b;

    std::cout << "a = "; a.print();
    std::cout << "b = "; b.print();
    std::cout << "a == b: " << (a == b ? "true" : "false") << std::endl;

    return 0;
}