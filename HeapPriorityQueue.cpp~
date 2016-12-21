//HeapPriorityQueue.cpp
#ifndef _HEAPPRIORITYQUEUE_CPP
#define _HEAPPRIORITYQUEUE_CPP

#include "HeapPriorityQueue.hpp"
#include <cassert>
#include <cstdlib>//for NULL
#include <iostream>

HeapPriorityQueue::HeapPriorityQueue() {
  // Empty... nothing needs to be done.
}

HeapPriorityQueue::~HeapPriorityQueue() {
  // no clean-up to do, since the heap is not dynamically allocated
}

void HeapPriorityQueue::swapUp(int i) {
if (i==0) return;
int p = (i-1)/2;
if (heap[i]->getBadness() < heap[p]->getBadness()) {
PuzzleState* tmp = heap[i];
heap[i] = heap[p];
heap[p] = tmp;
swapUp(p);}
}


void HeapPriorityQueue::put_in(PuzzleState *elem) {
  // TODO:  Put your code here!
heap.push_back(elem);
swapUp((int)heap.size()-1);
}


void HeapPriorityQueue::swapDown(int i) {
int s = i;
int left = i * 2 + 1;
int right = left + 1;
int n = (int)heap.size();
if (left < n && (heap[left]->getBadness() < heap[s]->getBadness()))
{s = left;}
if (right < n && (heap[right]->getBadness() < heap[s]->getBadness()))
{s = right;}
if (s != i) {
PuzzleState* tmp = heap[i];
heap [i] = heap[s];
heap[s] = tmp;
swapDown(s);}
}

PuzzleState * HeapPriorityQueue::take_out() {
  assert(!is_empty());
  // TODO:  Put your code here!
PuzzleState* returnVal = heap[0];
heap[0] = heap[(int)heap.size()-1];
swapDown(0);
return returnVal;
}


bool HeapPriorityQueue::is_empty() {
  return (heap.size() == 0);
}

int HeapPriorityQueue::parent(int index) {
  return (index - 1) / 2;
}

int HeapPriorityQueue::first_child(int index) {
  return 2 * index + 1;
}

bool HeapPriorityQueue::is_root(int index) {
  return index == 0;
}

bool HeapPriorityQueue::is_leaf(int index) {
  return num_children(index) == 0;
}

int HeapPriorityQueue::num_children(int index) {
  int fchild = first_child(index);
  return max(0, min(2, (int)heap.size() - fchild));
}

#endif
